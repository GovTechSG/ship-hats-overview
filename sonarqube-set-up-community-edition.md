# Set up SonarQube Community Edition


To set up SonarQube Community edition, complete the following steps:

1. [Retrieve App Key and Token ID](#retrieve-app-key-and-token-id)
2. [Configure Bamboo plan](#configure-bamboo-plan)
3. [Set up Sonar Scan for different languages](#sonar-scan-for-different-languages)
4. [Test Coverage](#test-coverage)

---

## Retrieve App Key and Token ID

Only **Project Admin (PA)** can get the details of SonarQube application. Please contact your **PA** to retrieve **App Key** and **Token ID**.

### Pre-requisites

- All Project Admins must log in to https://sonar.hats.stack.gov.sg/sonar with their SHIP LDAP credentials to trigger the account creation.
- This also applies to project admins that are added subsequently. In this case, the project admins must log in first before being assigned as a project admin. 

Failing to so may result in an error when either of the scenarios occurs:
- Creating new application (Sonarqube/Fortify)
- Adding a new user as project admin.

---

### To retrieve App Key and Token ID:

1. Go to https://www.ship.gov.sg, and then log in with your SHIP Credentials.

1.  Under **Projects**, click **All Projects**, and then click **Manage** on the desired project.

1.  Click the **QA & Security** tab.

    1.  (Optional) To create a new SonarQube application, go to the **SonarQube** section.

    2.  Click **+ Add another**, enter the required details, and then click **Add**.

    ![](hats-community-image1.png)

1.  In the **SonarQube** section, click **Manage**.

1.  Retrieve the **App Key** and **Token ID**.

    ![](hats-community-image2.png)

---


## Configure Bamboo plan

**Topics**
- [Configure Repositories (Bitbucket)](#configure-repositories-bitbucket)
- [Configure Variables](#configure-variables)
- [Configure Requirements](#configure-requirements)
- [Configure Tasks](#configure-tasks)

### Configure Repositories (Bitbucket)

1.  Sample repository from Bitbucket.

    ![](hats-community-image3.png)

1.  In **Plan configuration**, click **Repositories**, and then click **Add repository**.
    
    ![](hats-community-image4.png)

1.  Select **Bitbucket Server / Stash**.
    
    ![](hats-community-image5.png)

1.  In **Repository**, enter repository name, and then select the desired branch. The name choice is up to you.
    
    ![](hats-community-image6.png)

### Configure Variables

1.  In **Plan configuration**, click **Variables**.
1.  Add a variable ending with *secret* (for example **sonarqube_token_secret**).
1. In **Value**, enter the
    **Token ID** obtained in step 5 in the [To Retrieve App Key and Token ID](#to-retrieve-app-key-and-token-id) section. 

    ![](hats-community-image7.png)

### Configure Requirements

1.  In job configuration, in **Search for a capability**, add the necessary capability, and then select **Add**. For example:
    - For Linux, add **hats_linux_image** to exists.

        ![](hats-community-image8.png)
    - For Windows, add **hats_windows_image** to exists.

        ![](hats-community-image9.png)

1.  If the screen shows **No Agents**, create a ticket to request for HATS Linux or Windows Agent to be dedicated to the Bamboo Project or a specific plan.

### Configure Tasks

>**Note:** Do **not** use Sonar Plugin on  Bamboo. Use **Script**.

1.  In the job configuration, click **Tasks**, and then click **Add task**. 

    ![](hats-community-image10.png)

1.  Search for *source code checkout*, and then click **Source Code Checkout**.

    ![](hats-community-image11.png)

1.  Dropdown and select the repository configured in the [Configure Repositories](#configure-repositories-bitbucket) section. 
1. Select the **Force Clean Build** check box.

    ![](hats-community-image12.png)

1.  Click **Add Tasks** again, search for *script*, and then click **Script**.

    ![](hats-community-image13.png)

1.  Ensure the **Script** task is placed below the **Source Code Checkout** task.

1. In the description of **Tasks**, click *runtime, plan, project and global variables*. 

    ![](hats-community-image14.png)

1.  In the new window that appears, scroll down till you see **Plan variables** where you will find the token you configured in the [Configure Variables](#configure-variables) section. 
1. Copy the value from **Variable name**.
    
    ![](hats-community-image15.png)

1.  Copy the sonar scan script based on the language of your repository (Refer to samples in the [Sona Scan for different languages](#sonar-scan-for-different-languages) section below), and replace **Variable name** as the value of `-Dsonar.login=`

    >**Note:** Do **not** store the token as plaintext in the script.

    ![](hats-community-image16.png)

    >**Using variables in bash**
    >-   Bamboo variables are exported as bash shell variables. All full stops (periods) are converted to underscores.
    >-   For example, the variable `bamboo.my.variable` is `\$bamboo_my_variable` in bash. This is related to File Script tasks (not Inline Script tasks).

---

## Sonar Scan for different languages
**Topics**
- [Sonar Scan for Java](#sonar-scan-for-java)
- [Sonar Scan for MSBuild](#sonar-scan-for-msbuild)
- [Sonar Scan for Dotnet](#sonar-scan-for-dotnet)
- [Sonar Scan for Others](#sonar-scan-for-others)

### Sonar Scan for Java

- **Maven**

    1. Format to put **Script body** in step 7 in the [Configure Tasks](#configure-tasks) section:

        ```
        sonar-scanner \
        -Dsonar.projectKey=<App Key> \
        -Dsonar.sources=src/main/java \
        -Dsonar.java.binaries=target/classes \
        -Dsonar.language=java \
        -Dsonar.host.url=https://sonar.hats.stack.gov.sg/sonar \
        -Dsonar.login=<Token-from-SHIP-HATS-Portal>
        ```

        **Sample**
        ```
        sonar-scanner \
        -Dsonar.projectKey=hats_multi \
        -Dsonar.sources=src/main/java \
        -Dsonar.java.binaries=target/classes \
        -Dsonar.language=java \
        -Dsonar.host.url=https://sonar.hats.stack.gov.sg/sonar \
        -Dsonar.login=${bamboo.sonarqube_token_secret}
        ```

- **Gradle**

    - Current Sonarqube version : 8.9

    - Official documentation for the version 8.9
    <https://docs.sonarqube.org/8.9/analysis/scan/sonarscanner-for-gradle/>

    1. Declare org.sonarqube plugin in build.gradle in your repository

         ```
        plugins {

        id "org.sonarqube" version "<version">

        }
        ```

    1. Format to put **Script body** iin step 7 in the [Configure Tasks](#configure-tasks) section:
        ```
        gradle sonarqube \
        -Dsonar.projectKey=<App Key> \
        -Dsonar.host.url=https://sonar.hats.stack.gov.sg/sonar \
        -Dsonar.login=<Token-from-SHIP-HATS-Portal>
        ```

        **Sample**

        ```
        gradle sonarqube \
        -Dsonar.projectKey=hats_multi \
        -Dsonar.host.url=https://sonar.hats.stack.gov.sg/sonar \
        -Dsonar.login=${bamboo.sonarqube_token_secret}
        ```

### Sonar Scan for MSBuild

1. Format to put **Script body** in step 7 in the [Configure Tasks](#configure-tasks) section:

    ```
    # Start of scan

    sonar-scanner.bat -D"sonar.projectKey=<App Key from SHIP HATS self help portal>" -D"sonar.sources=." -D"sonar.host.url=https://sonar.hats.stack.gov.sg/sonar" -D"sonar.login=<Token-from-SHIP-HATS-Portal>"

    # Rebuild your solution

    MSBuild.exe <path to solution.sln> /t:Rebuild

    # End of scan

    SonarScanner.MSBuild.exe end /d:sonar.login="<token>"
    ```

### Sonar Scan for Dotnet

1. Format to put **Script body** in step 7 in the [Configure Tasks](#configure-tasks) section:

    ```
    # cd to the location where .csproj is located

    cd <path_to_csproj>

    # install dotnet-sonarscanner globally

    dotnet tool install --global dotnet-sonarscanner

    # begin sonar scan

    dotnet sonarscanner begin /k:$<App Key> /d:sonar.host.url=https://sonar.hats.stack.gov.sg/sonar  /d:sonar.login=<Token-from-SHIP-HATS-Portal>

    # build project

    dotnet build

    # end sonar scan

    dotnet sonarscanner end /d:sonar.login=<Token-from-SHIP-HATS-Portal>
    ```

    **Sample**

    ```
    # cd to the location where .csproj is located

    cd sample/sonarqube-scanner-dotnet/sampledotnet6

    # install dotnet-sonarscanner globally

    dotnet tool install --global dotnet-sonarscanner

    # begin sonar scan

    dotnet sonarscanner begin /k:${bamboo.sonarqube.projectKey} /d:sonar.host.url=${bamboo.hats.sonarqube.url} /d:sonar.login=${bamboo.sonarqube_community_portal_token_secret}

    # build project

    dotnet build

    # end sonar scan

    dotnet sonarscanner end /d:sonar.login=${bamboo.sonarqube_community_portal_token_secret}
    ```

### Sonar Scan for Others

1. For Typescript or projects requiring Node modules, add the following line before scan:

    **Typescript**
    ```
    export NODE_PATH=${bamboo.hats.node_modules.path}
    ```

1. Format to put **Script body** in step 7 in the [Configure Tasks](#configure-tasks) section:

    ```
    sonar-scanner \
    -Dsonar.projectKey=\<App Key from SHIP HATS Portal\> \
    -Dsonar.sources=. \
    -Dsonar.host.url=https://sonar.hats.stack.gov.sg/sonar \
    -Dsonar.login=<Token-from-SHIP-HATS-Portal\>
    ```

    **Sample**

    ```
    sonar-scanner \
    -Dsonar.projectKey=hats_multi \
    -Dsonar.sources=. \
    -Dsonar.host.url=https://sonar.hats.stack.gov.sg/sonar \
    -Dsonar.login=${bamboo.sonarqube_token_secret}
    ```

---

## Test Coverage

By default, your unit test results are not visible in your
SonarQube app. For the unit test coverage to be visible in your SonarQube app, you will need to provide the report path to the test coverage artifacts.

-   As each project uses different testing frameworks with different supported report format. Please refer to official SonarQube documentation on the types of Test Coverage report path provided that suits your project requirements.

-   Official Documentation:
    <https://docs.sonarqube.org/8.9/analysis/coverage/>

-   In this example, we use Jest Testing Framework as an example.

### Jest (Javascript Testing Framework)

Jest provides a `jest.config.js` file for configuration. To pass test coverage information to SonarQube, you need to provide the valid report format artifacts.

1. Indicate **lcov**  under the **coverageReporters**  parameter to have Jest generate the **lcov.info** as part of the coverage report artifacts.
    - By default, the coverage reports are stored under the directory named `coverage` 
    - The report path will be `coverage/lcov.info` 
    <br>

    **Configurations for generating the required test coverage report format**

    - The directory where Jest should output its coverage files

        ```coverageDirectory: \'coverage\',```

    - A list of reporter names that Jest uses when writing coverage reports

        ```coverageReporters: \[\'lcov\', \'text\', \'text-summary\', \'json\'\],```
    

1. Format to put **Script body** in step 7 in the [Configure Tasks](#configure-tasks) section. Make sure that you indicate the coverage files with the **-Dsonar.javascript.lcov.reportPaths** option.

    ```
    sonar-scanner \
    -Dsonar.projectKey=<App Key from SHIP HATS Portal\> \
    -Dsonar.sources=. \
    -Dsonar.host.url=https://sonar.hats.stack.gov.sg/sonar \
    -Dsonar.login=<Token-from-SHIP-HATS-Portal\> \
    -Dsonar.javascript.lcov.reportPaths=coverage/lcov.info
    ```

    **Sample**

    ```
    sonar-scanner \
    -Dsonar.projectKey=hats_multi \
    -Dsonar.sources=. \
    -Dsonar.host.url=https://sonar.hats.stack.gov.sg/sonar \
    -Dsonar.login=${bamboo.sonarqube_token_secret} \
    -Dsonar.javascript.lcov.reportPaths=coverage/lcov.info
    ```
