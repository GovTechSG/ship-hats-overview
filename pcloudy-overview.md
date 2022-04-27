# pCloudy Overview

pCloudy is an automated test farm that executes automated tests on browsers (such as desktop, mobile) and mobile apps. Mobile devices are managed via a desktop web browser. Automation is triggered from Bamboo using Robot Framework.

For more information on pCloudy Test Farm, see https://www.pcloudy.com/.


**Topics**  

<!--- [Roles and Permissions](#roles-and-permissions)-->
<!--- [Access pCloudy]()-->
- [Register Devices in Apple Developer Portal](pcloudy-register-devices)
- [pCloudy CLI](#pcloudy-cli)
- [FAQs](#faqs)
- [Additional Resources](#additional-resources)

<!--
## Roles and Permissions

-->

## Register Devices in Apple Developer Portal

**Topics**
- [Prerequisites](#prerequisites)
- [Retrieve UUID from pCloudy](#retrieve-uuid-from-pcloudy)
- [Register devices in the Apple Developer Account](#register-devices-in-the-apple-developer-account)
- [Additional Resources](#additional-resources)
### Prerequisites

- You must have access to the Apple Developer Account with has Apple Developer Program Membership
- You must have access to HATS pCloudy iOS devices

### Retrieve UUID from pCloudy
1. Log in to the device farm (https://hats.pcloudy.com)
1. Click on Devices > UUID, you will be able to see the list of iOS devices.

    <kbd>![UUID]()</kbd>


### Register devices in the Apple Developer Account
1. Log in to Apple Developer Program
1. Navigate to Certificates, Identifiers & Profile
1. Click on "Devices"
1. Register single devices or multiple devices (via device file)
Devices UI
    <kbd>![Register a New Device]()</kbd>

### Additional Resources
- Register a single device: https://help.apple.com/developer-account/#/dev40df0d9fa
- Register multiple devices: https://help.apple.com/developer-account/#/devebd34abb1

## pCloudy CLI

pCloudy CLI is a Command Line Interface(CLI) tool to be used as part of the Bamboo pipeline to help book and release devices on pCloudy.

**Topics**
- [Prerequisites]()
- [Retrieving your PCloudy Token]()
- [Setting up your Bamboo Plan]()
- [Upload Files (Optional)]()
- [Book Device]()
- [Expected Outputs]()
- [Run your tests]()
- [Download Tests Logs (Optional)]()
- [Release Device]()
- [CLI Documentation]()


### Prerequisites
- The user must be a Project Admin (PA) in order to retrieve the pCloudy token from the SHIP-HATS Self Help Portal.
- Make sure that your bamboo plan has an elastic image configuration of the HATS security agent dedicated to it (check with the HATS team)

### Retrieving PCloudy Token
To use the pCloudy CLI in bamboo, you would need to retrieve your pCloudy token from your pCloudy application from the SHIP-HATS Self Help portal.

1. Login to the SHIP-HATS Self Help Portal (https://www.ship.gov.sg)
1. Click Projects on the left side bar, "All Projects" and "Manage" on the project that your pCloudy application is in. If your pCloudy application is already created, you can jump to step 5. If you want to create a new pCloudy application, go to step 3.  

    <kbd>![All Projects]()
1. Click on QA & Security and Click Add tool  

    <kbd>![All Projects]()

1. Click on - Select tool - and select pCloudy Device Farm & HATS Browser Farm. Then add the tool

    <kbd>![All Projects]()

1. Wait for the tool to finish loading and appear on the webpage. Copy the pCloudy token

    <kbd>![All Projects]()


### Set up your Bamboo Plan

After you have your pCloudy token, you can use the pCloudy CLI in your bamboo plans, to book and release devices on pCloudy.

You can also use the pCloudy CLI to upload files to pCloudy.

### Upload Files
You can use the pCloudy CLI to upload files to pCloudy, with the command: `pcloudy-cli upload-file`. This is an optional step.

This is mainly used to upload your application to pCloudy for testing.

- You need your token for this command
- The name of the uploaded file may be different from the original name of the file
- The file cannot be empty
- The file can only have the extensions of `.zip` , `.apk`, or `.ipa`. 
- The name of the file may only contain the alphanumeric characters and ( `-` , `_` , `.` ) characters

The required options are:
- --pcloudy-token, -P
- --file, -f

<!-- tabs:start -->
### **Command Format**

```
pcloudy-cli upload-file -P <your pCloudy Token> -f <Path to file to upload>
``` 
 
**Example: Upload a test build of an Android application to pCloudy**
```
pcloudy-cli upload-file -P "$token" -f artifacts/test_build_12_21.apk
```

### **Output Format**

If successful, the command would exit successfully with a stdout of:

```
{"uploaded_filename": "STRING"}
```

**Example pcloudy-cli upload-file -P "$token" -f artifacts/test_build_12_21.apk**
```
>> {"uploaded_filename": "test_build_12_21-1637507508.apk"}
```

You can then use a tool like `jq`  or `awk`  or `grep`  to get the data you want out of the stdout.

<!-- tabs:end -->



<details>
 <summary> <b>Syntax</b></summary><br>

**Command Format**

```
pcloudy-cli upload-file -P <your pCloudy Token> -f <Path to file to upload>
``` 
 
**Example: Upload a test build of an Android application to pCloudy**
```
pcloudy-cli upload-file -P "$token" -f artifacts/test_build_12_21.apk
```

If successful, the command would exit successfully with a stdout of:

**Output Format**
```
{"uploaded_filename": "STRING"}
```

**Example pcloudy-cli upload-file -P "$token" -f artifacts/test_build_12_21.apk**
```
>> {"uploaded_filename": "test_build_12_21-1637507508.apk"}
```

You can then use a tool like `jq`  or `awk`  or `grep`  to get the data you want out of the stdout.
 </details>


---



### Book Device
Regardless of whether you upload your test file or not to pCloudy, you can use the pCloudy CLI to book a device for testing.

- You need your token for this command
- This command will return you the rid  (used for releasing the booked device early) and the api_endpoint (the appium endpoint you would use to run your robots tests)
- You can choose between browser testing or application testing  

The required options are:
- --pcloudy-token, -P
- --duration, -d
- --platform, -p

Ensure that at least one of these options are used to set the test type of the booked device:
- --app-name, -a
- --browser, -b

Optional options:
- --platform-version
- --device-name

<details>
 <summary> <b>Broswer Testing</b></summary><br>

**Command Format** 
```
pcloudy-cli book-device \
    -P <your pCloudy Token> \
    -d <duration to book the device (minutes)> \
    -p <device platform, [ios,android]> \
    -b # -b for browser based tests
```
**Android Example: Book Android device for browser testing, 10 minutes**
```
pcloudy-cli book-device -P "$token" -d 10 -p android -b
```

**iOS Example: Book iOS device for browser testing, 10 minutes**
```
pcloudy-cli book-device -P "$token" -d 10 -p ios -b
```

 </details>

--- 
<details>
 <summary> <b>App Testing</b></summary><br>

**Command Format**
```
pcloudy-cli book-device \
    -P <your pCloudy Token> \
    -d <duration to book the device (minutes)> \
    -p <device platform, [ios,android]> \
    -a <filename of app to test> # -a for app based tests
```    
**Android Example: Book Android device for app testing, 20 minutes**  

Ensure the package file to be in the current directory
```
pcloudy-cli book-device -P "$token" -d 20 -p android -a "demo_app.apk"
```
**iOS Example: Book iOS device for app testing, 20 minutes**  

Ensure the package file to be in the current directory
```
pcloudy-cli book-device -P "$token" -d 20 -p ios -a "demo_app.ipa"
```
 </details> 

---

<details>
 <summary> <b>Additional (Optional) Parameters</b></summary><br>

**Book specific device based on platform version: Book specific iOS device with platform version 14.1.0**  

```
pcloudy-cli book-device -P "$token" -d 20 -p ios -b --platform-version "14.1.0"
```

**Book specific device based on device full name**
```
pcloudy-cli book-device -P "$token" -d 20 -p ios -b --full-name "Apple_iPhoneXR_Ios_14.4.0_f1c43"
```
 </details> 

---

### Expected Outputs

If the command ran successfully, you should get a stdout of:



<details>
 <summary> <b>Output Format</b></summary><br>

```
{"rid": "INTEGER", "api_endpoint": "STRING, Appium Endpoint", ...other device information}
``` 
 
**Example**
```
pcloudy-cli book-device -P 6ba4b6d2f0fecc6f2b9ee16bee2d2eb8 -d 10 -p ios -b
>> {"duration": 10, "platform": "ios", "full_name": "Apple_iPhoneXR_Ios_14.4.0_f1c43", "version": "14.4.0", "rid": "52485", "platform_name": "Ios", "browser_name": "14", "device_name": "14", "appium_endpoint": "https://hats.pcloudy.com/appium/hubble/n6nn6382nbnf-6643"}
```

You can then use a tool like jq  or awk  or grep  to get the data you want out of the stdout.

 </details>




--- 


### Run your tests
**Sample Test Script**  

After booking the device (and optionally uploading your apk file), you can run additional commands to perform your pCloudy tests. In this case, we are using Robot Framework as the testing framework in this example.

In this test script, we are running mobile browser testing.
This script is saved into a test file named `test.txt`.


<details>
 <summary> <b>[BROWSER TESTING] Sample Robot Framework Test Script</b></summary><br>

**Settings**
```
Documentation    To test basic demo app
 
Library          AppiumLibrary
```

**Keywords**
```
Do Google Search
    Go To Url   https://www.google.com
    Input text  //input[@aria-label="Search"]   "pCloudy"
    Press Keycode  66
```

**Test Cases**
```
Launch Browser Init
    Open Application  ${ENDPOINT}  platformName=Android  browserName=Chrome  deviceName=${DEVICE_ID}  pCloudy_EnableVideo=true  pCloudy_EnablePerformanceData=true  pCloudy_EnableDeviceLogs=true
Search for something on Google
    Do Google Search
Close All Apps
    Close All Applications
```


 </details>

<br>

Note that the sample APK file is already uploaded with the name of `pCloudyAppiumDemo.apk`

- If you upload a package file with the same filename, the filename will be appended with a random numerical identifier by default - e.g, ` pCloudyAppiumDemo-1638321800.apk`
- Value of the APP_PACKAGE use `com.pcloudy.appiumdemo`

<details>
<summary><b>[APP TESTING] Sample Robot Framework Test Script</b></summary>

**Settings**

```
Library         AppiumLibrary
```

**Keywords**
```
Launch App Init
    Open Application  ${ENDPOINT}  platformName=Android  platformVersion=${VERSION}  deviceName=${DEVICE_ID}  appPackage=${APP_PACKAGE}  pCloudy_EnableVideo=true  pCloudy_EnablePerformanceData=true  pCloudy_EnableDeviceLogs=true
 
Book a flight
    Click Element   id=com.pcloudy.appiumdemo:id/accept
    Log To Console  Accept Button is clicked
 
    Wait Until Page Contains Element  id=com.pcloudy.appiumdemo:id/flightButton  20
    Click Element   id=com.pcloudy.appiumdemo:id/flightButton
    Log To Console  Book a flight button clicked
 
    Wait Until Page Contains Element  id=com.pcloudy.appiumdemo:id/spinnerfrom  20
    Click Element   id=com.pcloudy.appiumdemo:id/spinnerfrom
    Log To Console  From location drop down is clicked
 
    Wait Until Page Contains Element  //*[@id="android:id/text1" or @text="Bangalore, India (BLR)"]  20
    Click Element   //*[@id="android:id/text1" or @text="Bangalore, India (BLR)"]
    Log To Console  From Location is selected
 
    Click Element   id=com.pcloudy.appiumdemo:id/spinnerto
    Log To Console  To location drop down is clicked 
    Capture Page Screenshot
 
    Click Element   //*[@id="android:id/text1" or @text="Pune, India (PNQ)"]
    Log To Console  To location is selected
 
    Click Element   id=com.pcloudy.appiumdemo:id/singleTrip
    Log To Console  One way trip is selected
 
    Click Element   id=com.pcloudy.appiumdemo:id/txtdepart
    Log To Console  Departure time is selected
 
    Wait Until Page Contains Element  //*[@id="android:id/button1" or @text="OK"]  20
    Click Element   //*[@id="android:id/button1" or @text="OK"]
    Log To Console  Okay button is selected
 
    Wait Until Page Contains Element  com.pcloudy.appiumdemo:id/searchFlights  20
    Click Element   com.pcloudy.appiumdemo:id/searchFlights
    Log To Console  Search flight button is clicked
    Capture Page Screenshot
```

**Test Cases**

``` 
Test booking flight
    [Documentation]  As a user
    ...    I want to book a flight
    Launch App Init
    Book a flight
Close All Apps
    Close All Applications
```

 </details>

---


**Passing Parameters into Test Script**

To run the Robot Framework script, you will need to provide the Appium Endpoint and deviceName to the `Open Application` keyword in order to connect to pCloudy remote devices.

 <details>
<summary><b>[BROWSER TESTING] Bamboo Script Task to run Robot Framework tests</b></summary>

Line 2 ~ 5 are the retrieval of the parameters to pass into your test
```
OUTPUT=$(pcloudy-cli book-device -P "$token" -p android -d 15 -b)
RID=$(echo "$OUTPUT" | jq -r ".rid")
APP_URL=$(echo "$OUTPUT" | jq -r ".appium_endpoint")
DEVICE_ID=$(echo "$OUTPUT" | jq -r ".device_name")
``` 
 
The sample robot framework script above is saved in the file `test.robot`
```
robot --variable ENDPOINT:"$APP_URL/wd/hub" --variable DEVICE_ID:"$DEVICE_ID" test.robot
```

 </details>

 <details>
<summary><b>[APP TESTING] Bamboo Script Task to run Robot Framework tests</b></summary>

Line 2 ~ 5 are the retrieval of the parameters to pass into your test
```
OUTPUT=$(pcloudy-cli book-device -P "$token" -p android -d 15 -b)
RID=$(echo "$OUTPUT" | jq -r ".rid")
APP_URL=$(echo "$OUTPUT" | jq -r ".appium_endpoint")
DEVICE_ID=$(echo "$OUTPUT" | jq -r ".device_name")  
``` 

The sample robot framework script above is saved in the file `testapp.robot`
```
robot --variable ENDPOINT:"$APP_URL/wd/hub" --variable DEVICE_ID:"$DEVICE_ID" \
--variable APP_PACKAGE:'com.pcloudy.appiumdemo' --variable VERSION:"$VERSION" testapp.robot
```

 </details> 

---

### Download Tests Logs
After your tests are complete you can also download the logs from pCloudy using the pcloudy-cli download-logs-data  command. This is an optional step.

- You will need your pCloudy Token and `rid`  used to book the device
- The logs will also be based on the tests ran on the booked device
- Log files will be downloaded into the bamboo agent, where you can persist them by saving them as bamboo artifacts.

<details>
<summary><b>Command Format</b></summary>

```
pcloudy-cli download-logs-data -P <your pCloudy Token> -r <rid string when the device was booked>
``` 
 
**Example: Download the logs of tests ran on booked device with rid of 52485**
```
pcloudy-cli download-logs-data -P "$token" -r 52485
```
 </details>



If successfuly, the command would exit successfully with a stdout of:

<details>
<summary><b>Output Format</b></summary>

```
{"success_logs": ["STRING", ...], "failed_logs": ["STRING", ...]}
```

**Example**
```
pcloudy-cli download-logs-data -P "$token" -r 52485
>> {"success_logs": [".pcloudy_appium_logs/52485/cpu.txt", ".pcloudy_appium_logs/52485/mem.txt", ".pcloudy_appium_logs/52485/net.txt", ".pcloudy_appium_logs/52485/bat.txt", ".pcloudy_appium_logs/52485/appium_stdout.txt", ".pcloudy_appium_logs/52485/appium_stderr.txt"], "failed_logs: [".pcloudy_appium_logs/52485/log.txt"]}
```
 </details>

The downloaded logs will be stored in the current project's directory , in the bamboo agent, with a format of:  

 <details>
<summary><b>Directory Sturcture Format</b></summary>

```
./.pcloudy_appium_logs
|-- rid (NUMBER)
|   |-- *.txt (log files)
|   `-- ...
`-- ...
```


**Example**
```
./.pcloudy_appium_logs
`-- 52485
    |-- appium_stderr.txt
    |-- appium_stdout.txt
    |-- bat.txt
    |-- cpu.txt
    |-- log.txt
    |-- mem.txt
    `-- net.txt
```

 </details>

### Release Device
After your tests are complete and you want to release the booked device, you can run the pcloudy-cli release-device  command.

- You will need to use the same token and rid  when booking the device
    
    <details>
    <summary><b>Command Format</b></summary>
    <br>

    ```
    pcloudy-cli release-device -P <your pCloudy Token> -r <rid string when the device was booked>
    ```

    **Example: Release a booked device with an rid of 52485**
    ```
    pcloudy-cli release-device -P "$token" -r 52485
    ```

    </details>

- If successfuly, the command would exit successfully with a stdout of:

    <details>
    <summary><b>Command Format</b></summary>
    <br>

    ```
    {"rid": "INTEGER"}
    ```

    **Example**
    ```
    pcloudy-cli release-device -P "$token" -r 52485
    >> {"rid": "52485"}
    ```
    </details>



## CLI Documentation

|Command Name|pcloudy-cli|
|---|---|
|Synopsis	|pcloudy-cli --help --version/-V
Example|	pcloudy-cli --help<br>pcloudy-cli -V
Description	|Base command for pCloudy CLI, should only be used in debugging situations.

|Options|Description|
|---|---|
--help	|Show the various options for the command and their respective descriptions
--version, -V	|Shows the version of the pCloudy CLI you are using

---

|Command Name|pcloudy-cli upload-file|
|---|---|
Synopsis	|pcloudy-cli upload-file --pcloudy-token/-P <pcloudy_token> --file/-f <PATH>
Example	|pcloudy-cli upload-file -P 6ba4b6d2f0fecc6f2b9ee16bee2d2eb8 -f artifacts/test_build_12_21.apk
Expected Output|	{"uploaded_filename": "test_build_12_21-1637507508.apk"}
Description	|pCloudy CLI command used to upload a file to pCloudy

|Options|Description|
|---|---|
--help	|Show the various options for the command and their respective descriptions
--pcloudy-token, -P <TEXT>	|The SHIP-HATS subscription's project's pcloudy application token.
--file, -f <PATH>	|The path to the file to upload to pCloudy
---


|Command Name|pcloudy-cli book-device|
|---|---|
Synopsis	|pcloudy-cli book-device --pcloudy-token/-P <pcloudy_token> --duration/-d <integer> --platform/-p <ios|andriod> --app-name/-a <app_name(optional)> --browser/-b(optional) --platform-version <platform_version(optional)> --device-name <device_name (optional)>
Example	|pcloudy-cli book-device -P 6ba4b6d2f0fecc6f2b9ee16bee2d2eb8 -d 10 -p ios -b
Expected Output	|{"duration": 10, "platform": "ios", "full_name": "Apple_iPhoneXR_Ios_14.4.0_f1c43", "version": "14.4.0", "rid": "53257", "platform_name": "Ios", "browser_name": "14", "device_name": "14", "appium_endpoint": "https://hats.pcloudy.com/appium/hubble/n6nn6382nbnf-6643"}
Description	|pCloudy CLI command used to book a device on pCloudy, using the pCloudy token generated from a SHIP-HATS subscription

|Options|Description|
|---|---|
--help	|Show the various options for the command and their respective descriptions
--pcloudy-token, -P <TEXT>	|The SHIP-HATS subscription's project's pcloudy application token.
--duration, -d <INTEGER>|The duration you want to book the device for
--platform, -p [ios/android]	|The platform of the device to book (Either ios/android )
--app-name, -a <TEXT> (Optional)	|Name of app to be used and test on the booked device (Used to set test type of booked device)
--browser, -b (Optional)	|Set the test type of the booked device to be browser (Used to set test type of booked device)
--platform-version <TEXT> (Optional)	|Filter devices by the platform version given to be booked
--full-name <TEXT> (Optional)|	Filter devices by the device name given to be booked
---


|Command Name|pcloudy-cli download-logs-data|
|---|---|
Synopsis	|pcloudy-cli download-logs-data --pcloudy-token/-P <pcloudy_token> --rid/-r <rid>
Example	|pcloudy-cli download-log-data -P 6ba4b6d2f0fecc6f2b9ee16bee2d2eb8 -r 52485
Expected Output	|{"success_logs": [".pcloudy_appium_logs/52485/cpu.txt", ...], "error_logs": [".pcloudy_appium_logs/52485/log/txt", ...]}
Description	|pCloudy CLI command used to download log data after tests

|Options|Description|
|---|---|
--help	|Show the various options for the command and their respective descriptions
--pcloudy-token, -P <TEXT>	|The SHIP-HATS subscription's project's pcloudy application token.
--rid, -r <TEXT>	|The rid of the booked device
---


|Command Name|pcloudy-cli release-device|
|---|---|
Synopsis	|pcloudy-cli release-device --pcloudy-token/-P <pcloudy_token> --rid/-r <rid>
Example	|pcloudy-cli release-device -P 6ba4b6d2f0fecc6f2b9ee16bee2d2eb8 -r 52485
Expected Output	|{"rid": "53257"}
Description	|pCloudy CLI command used to release a booked device early on pCloudy

|Options|Description|
|---|---|
--help	|Show the various options for the command and their respective descriptions
--pcloudy-token, -P <TEXT>	|The SHIP-HATS subscription's project's pcloudy application token.
--rid, -r <TEXT>	|The rid of the booked device to be released early

---

## Automated Testing
Please refer to [pCloudy CLI](https://confluence.ship.gov.sg/x/Foo4IQ) tool to get started with mobile automated testing.

If you need technical assistance on connecting to pcloudy devices, please raise a service request [here](https://jira.ship.gov.sg/servicedesk/customer/portal/11/create/149).

## Manual Testing
### Prerequisites
To access the [pCloudy web dashboard](https://hats.pcloudy.com), make sure you have the following:
- SHIP VPN
- Internet access and Firefox browser/ Firefox Developer Edition browser, preferably on a non-government issued laptop/ development laptop
- The required proxy configuration will be provided during on-boarding.

As the dashboard can only be accessed via the proxy:
- We strongly recommend the use of Firefox browser as it is tied to browser-level settings. If Chrome is used, it will affect the system-level settings.
- Please note that only pCloudy site will be accessible, all other Internet sites are blocked. Unauthorized access to other websites are being monitored and logged.

>**Notes:**
>- Applicable for users doing manual testing - the account password will expire every year.
>- The current video format provided is in FLV. The pCloudy team is working on making the default video format to be MP4.
>- The devices in pCloudy are not meant to be used to develop functional testing script. Please use emulators/simulators from Android Studio and Xcode for respective OS.
>- When installing an app on an iOS device the app has to be re-signed with the UDID of the device. If you are unable to do the automated resigning, then you can resign manually using the UDID. You can copy the UDID and paste it in your Apple Developer account to resign manually
>- Please raise a service ticket for us to dedicate a Linux elastic agent to your Bamboo plan. The  elastic agent dedicated would have pcloudy-cli and another required packages installed.
>- When developing your functional testing scripts with Robot Framework, please do note the versions of Python and the following packages:  
    >- Appium Server, v1.19
    >- Python, v3.8.5 and above
    >- Robot Framework, v3.2.2 OR pabot, v1.10.0

### Usage of Pabot

Pabot allows parallel execution of tests. However, there is a known issue where the path of the embedded screenshots in the log file does not align with the filepath of the screenshots taken when tests fail. They are stored under the `pabot_results/` folder instead.

We strongly encouraged you to use Robot Framework i.e. `robot` command, where the screenshots are well embedded into the HTML report generated.




## FAQs

- **What testing frameworks are supported by pCloudy?**

    Please refer to the official documentation for more information: https://www.pcloudy.com/app-testing-tools-and-frameworks-integration/

- **Is there email restriction?**

    No, there is no email restriction for user sign up for manual testing.
Please raise a service ticket as we will only accept pending user registration strictly based on the signup email stated in the ticket.

- **Do we need to have any secure links whitelisted to be accessible through pCloudy device farm?**

    You will be able to connect to the devices via SHIP Bamboo for automated testing. If you want the devices to be able to access your UAT environment, you can whitelist the static public IP address 202.55.81.214, that the mobile devices identified by.


- **Are pCloudy devices hosted in GovTech data center or vendor’s location?**   
    
    The devices are being located at the vendor's data center in Singapore.

## Additional Resources
- Register a single device: https://help.apple.com/developer-account/#/dev40df0d9fa
- Register multiple devices: https://help.apple.com/developer-account/#/devebd34abb1
