# Bamboo Overview

Bamboo helps you build a continuous integration and continuous delivery pipeline. 

- Continuous Integration enables constant merging and testing of code, which leads to finding defects early and saves time on fixing merge issues. Development teams also receive rapid feedback on their work.
- Continuous Delivery enables you to deliver software solutions to production and testing environments to help organizations quickly fix bugs and respond to ever-changing business requirements. Bamboo provides following features:
    - Automated building and testing of software
    - Reporting tools for statistical analysis
    - Visibility info, and control over release artifacts and environments  

For more information on Bamboo, refer to https://www.atlassian.com/software/bamboo.

**Topics**  

- [Roles and Permissions](#roles-and-permissions)
- [Install a Remote Agent](#install-a-remote-agent)
- [Upgrade Remote Agent](#upgrade-remote-agent)
- [Create an Elastic Agent](#create-an-elastic-agent)
- [Register an Elastic Agent](#register-an-elastic-agent)
- [Base Elastic Agent AMI](#base-elastic-agent-ami)
- [Fair Usage Guidelines for Elastic Agents](#fair-usage-guidelines-for-elastic-agents)
- [FAQs](#bamboo-faqs)

## Roles and Permissions

A [SHIP-HATS Project Admin (PA)](user-roles-permissions) can add Atlassian Bamboo to a SHIP-HATS project. After you add Bamboo as your project tool, a Bamboo project is created. For more information on possible permissions for users added to the project, refer to [Bamboo project permissions](https://confluence.atlassian.com/bamboo/bamboo-permissions-369296034.html).

**Topics**
- [SHIP-HATS - Bamboo Role Mapping](#ship-hats---bamboo-role-mapping)
- [Bamboo Users](#bamboo-users)
- [View Project Permissions](#to-view-project-permissions)
- [Bamboo User Access](#bamboo-user-access)
- [Bamboo Group Access](#bamboo-group-access) 

### SHIP-HATS - Bamboo role mapping

| SHIP-HATS User  | Bamboo User |
| ---------------  |-------------|
| Project Admin (PA)| Administrator for the project. </br>This role is assigned by default when Bamboo is added to the SHIP-HATS project. Administrator can assign project roles to other users and there can be more than one Administrator. |
| Users | SHIP-HATS users can be assigned as an administrator or added as a user to the project. |

### Bamboo Users
You can add and manage users as individual users and group. Administrator can view **Project permissions** assigned for users and groups.

### To view project permissions:
1. In <a href="https://bamboo.ship.gov.sg/">SHIP Bamboo</a>, go to **Projects** and choose your project.   

    ![bamboo](bamboo.png)

1. Click ![settings](settings.png) **Project settings**. If you do not have Admin permissions, you will not be able to view this option.  

    ![bamboo2](bamboo2.png)
    
1. From the sidebar, select **Project permissions**. You will be able to view the **Project permissions**.

### Bamboo User access
Administrator can add users individually and manage their permissions.

### Bamboo Group access 
Groups are an easier and efficient way to manage user access for multiple users. 
Users can raise a <a href="https://jira.ship.gov.sg/servicedesk/customer/portal/11/">service request</a> with the required group name, project name and user details such as name and email address. Crowd administrator in the SHIP-HATS team evaluates the request and approves it accordingly.  

If approved, the group is created with the agency name prefixed to it. For example, *govtech-codex-documentation*. If a group was already created for managing users in any one of the Atlassian products added to your project on SHIP-HATS, you would be able to see that in all the integrated Atlassian products. Bamboo project administrators can manage user groups for this project.

## Install a Remote Agent

### Prerequisites
1.	Make sure that you have Java Runtime Environment 8.0 installed on the agent machine.
2.	Download the remote agent JAR file to a directory on the agent machine.

### Run a remote agent 
After you have installed the remote agent, run the remote agent by executing the following command line from the directory containing the remote agent jar file:  

    `java -jar atlassian-bamboo-agent-installer-8.0.6.jar https://bamboo.ship.gov.sg/agentServer/`

This will start a service wrapper for your agent, which will automatically restart in case of failure. You may also add extra system properties like `-Dbamboo.home=...` to customize the home location of the agent.


For more information, refer to the [Atlassian](https://confluence.atlassian.com/bamboo0800/bamboo-remote-agent-installation-guide-1077778446.html) documentation. 

### Register a remote agent
- Create a SHIP Service Ticket for Agent Approvals with UUID information.  

    ![Sample Information](bamboo-remote-agent-register-sample.png)


## Upgrade Remote Agent 

### To uplgrade remote agent after Bamboo version 8.0.6 is deployed:

If you already ran with `6.10.4 JAR` file, you can skip these steps as `6.10.4 JAR` is compatible with `8.0.6`.

1.	Stop the original agent.
2.	Backup the `BAMBOO_AGENT_HOME/conf/wrapper.conf` file.
3.	Remove the `BAMBOO_AGENT_HOME/conf` directory.
4.	Download a new Remote Agent JAR from your Bamboo Server: `atlassian-bamboo-agent-installer-8.0.6.jar` (Via SHIP VPN), and then rename it as `atlassian-bamboo-agent-installer-8.0.6.jar`
5.	Launch the remote agent: `java -jar atlassian-bamboo-agent-installer-8.0.6.jar` https://bamboo.ship.gov.sg/agentServer/
    
    This will create new `wrapper.conf` file. If you want to re-enact your custom configuration in that file, you can do it now.

### To register the remote agent, agency must complete the following steps:

1. Provide the following information:
    - Remote Agent IP Address Range
    - Remote agent connectivity method (VPN, endpoints etc)
1. Declare controls applied on the following: 
    - Bamboo user privileges has been properly assessed to not have more privilege than it requires
    - Remote agent is not able to reach where its not meant to
    - SSH / IAM credentials required — is this a good security practice? the downside is that credentials need to be exposed in bamboo / code.
    - Clean your workspace after every deployment
1.	Create a SR for approving the Remote agent with the UUID 
1.	After the agent is approved, Agency needs to provide the agent name so that SHIP-HATS team can rename the agent with the correct billing account and dedicate it to the Agency's project.


## Create an Elastic Agent

### Prerequisites

- Make sure that you are a [Subscription Admin (SA), a Project Admin (PA), or a Developer](user-roles-permissions).
- Make sure that you provision for Bamboo Remote Agent. Bamboo Remote Agent is an add-on tool, which is not part of the standard subscription. Ensure that you have a sufficient quota of bamboo agents subscribed. If there are none subscribed/insufficient quota, SA will need to subscribe/increase the quota by raising a [service request](https://jira.ship.gov.sg/servicedesk/customer/portal/11) ticket. 
- [Install the Remote Agent](#install-a-remote-agent)
- [Set up VPC Endpoint Connections](). This is required if you are setting up an agent in AWS, you can leverage VPC endpoints to connect to VPC endpoint services provided by SHIP. You must create VPC endpoints for SHIP's endpoint services in the same VPC as the DevOps zone.  
    Note the following requirements:
    -	Bamboo and Bamboo Broker endpoints services are required to register Bamboo agents.
    -	Bitbucket and Bitbucket endpoint services are required to check out configuration and deployment scripts.
- Set up Machine VPN. This is required if you are setting up an agent outside AWS (e.g. Azure) or if you cannot leverage VPC endpoints to connect to VPC endpoint services provided by SHIP.  
    Complete the following steps:  
    1.	Submit a [service request](https://jira.ship.gov.sg/servicedesk/customer/portal/11) to SHIP for OpenVPN Client config file for the Bamboo agent. This config file should not require password authentication. 
    2.	[Install OpenVPN client](https://openvpn.net/vpn-server-resources/how-to-connect-to-access-server-from-a-linux-computer/). 

>**Note:** Based on the prerequisites mentioned above, [raise a service request ticket](https://jira.ship.gov.sg/servicedesk/customer/portal/11) as needed.

### To create an Elastic Agent:

1. Go to **Agent** > **Elastic Agent : Manage elastic image configurations**.
1. Go to the bottom of the page and enter the required values.

    <kbd>![Elastic Image Configuration Details]()

1. Select the **Use Virtual Private Cloud** check box, and then select the following Subnets.

    <kbd>![Subnets]()</kbd>

>**Notes:**
>- The Latests AMI IDs can find in this page : [SHIP Bamboo Elastic Agent for SHIP Users - SHIP - SHIP Confluence](https://confluence.ship.gov.sg/display/SHIP/SHIP+Bamboo+Elastic+Agent+for+SHIP+Users).
>- Use the default instance type as T3 Burstable Performance Large (Unless the tenants having).
>- Make sure to select the correct subnets.

## Register an Elastic Agent

### To register and elastic agent:
1.	The SHIP Bamboo golden image is configured to have the required capabilities (as shown below). We highly recommend using SHIP Bamboo Base Image as it will reduce the effort to test and build your own image and this image is constantly enhanced and scanned to ensure no security vulnerabilities. 
2.	Agencies having specific requirements could reach out to SHIP team to request for software that is not available in the base AMI.
3.	For those with exception and need to configure the elastic agent by themselves, after consulting SHIP team, following AMI could be used by launching the instance and configuring required softwares. 
4.	Once the softwares are installed, create the image and share the image to SHIP GCC account (726262972162).  Make sure that the root volume is having the setting "Delete on termination"  when you are creating the AMI. 
5.	If you already have a snapshot pre-prepared, then simply share the image to us.
6.	Please make sure that the "Add 'create volume' permission to the following associated snapshots when creating permissions" is selected when you share the AMI with SHIP  
    
    <kbd>![Modify Image Permissions](bamboo-elastic-agent-modify-image-permission.png)

7.	Raise a Service Desk ticket for adding this image to your agent. We will then scan the image and if there is no vulnerabilities we will update the AMI to your agent. If there is vulnerability issue, we will let you know and you have to fix it and share it back to us..
8.	We will keep updating our base image whenever we upgrade our bamboo server or if we get notified for any security vulnerability issues. 

## Base Elastic Agent AMI

**Topics**

- [Base Linux Elastic Image (version 6.10.4 build 61009)](#base-linux-elastic-image-version-6104-build-61009)
- [Base Windows Elastic Image (version 6.10.4 build 61009)](#base-windows-elastic-image-version-6104-build-61009)
- [Base Linux Elastic Image (version 7.2.2)](#base-linux-elastic-image-version-722)
- [Base Linux Agent Image Capabilities](#the-base-linux-agent-image-capabilities)
- [Base HATS Windows Elastic Image (version 7.2.2 build 70209) source](#base-hats-windows-elastic-image-version-722-build-70209-source)
- [Base HATS Windows Agent Image Capabilities](#base-hats-windows-agent-image-capabilities)
- [Base Windows Agent Package Versions](#base-windows-agent-package-versions)

### Base Linux Elastic Image (version 6.10.4 build 61009)
|Environment|	Platform|	AMI#|	Last Update Date	|Capabilities in-build|
|---|---|---|---|---|
|Prod/UAT/Dev|	Linux 	|ami-0f6e0e0d27bb8700d|	 27 Feb 2021|docker -version 19.03.6<br><br>docker-compose -version 1.25.0<br><br>Node v8.10.0<br><br>JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64<br><br>JAVA -version 1.8.0_282|

### Base Windows Elastic Image (version 6.10.4 build 61009)
<br>


>**Note:** We have encountered users having difficulty accessing the ec2 instances based of these AMI. Use Large instance sizes for optimal performance.

|Environment|Platform|Netcore|AMI#|	AWS Visibility|Latest Patch Level|Elastic Agent Version|
|---|---|---|---|---|---|---|



|Environment|Platform|Netcore|AMI#|	AWS Visibility|Latest Patch Level|Elastic Agent Version|
|---|---|---|---|---|---|---|
|Dev / GCC Prod|Windows|Netcore 31 MSbuild 16|ami-080c9eadfa32623af (04-04-2022)<br><br>[ami-0654a797b21f3b2fe](https://ap-southeast-1.console.aws.amazon.com/ec2/v2/home?region=ap-southeast-1#ImageDetails:imageId=ami-0654a797b21f3b2fe) (17-02-2022) <br><br>[ami-0da6744c404a4eb49](https://ap-southeast-1.console.aws.amazon.com/ec2/v2/home?region=ap-southeast-1#ImageDetails:imageId=ami-0654a797b21f3b2fe) (14-12-2021)|Public|Apr-2022|6.21|
|Dev / GCC Prod|Windows|Netcore 22 MSbuild 15|ami-09589f812ce820c6b (04-04-2022)<br><br>[ami-08045c912e58aa213](https://ap-southeast-1.console.aws.amazon.com/ec2/v2/home?region=ap-southeast-1#ImageDetails:imageId=ami-08045c912e58aa213) (17-02-2022)<br><br>[ami-0df3811b1877e9cd3](https://ap-southeast-1.console.aws.amazon.com/ec2/v2/home?region=ap-southeast-1#ImageDetails:imageId=ami-0df3811b1877e9cd3) (14-12-2021)|Public|Apr-2022|6.21|

### Base Linux Elastic Image (version 7.2.2)

Please update your plans to match with the path stated below. Since we have multiple version of softwares installed , it is always good to check the version of the software set default and update your script to the version you require. For ex. we have Java 8 and 11 installed in our SHIP AMI and by default the JAVA_HOME points to Java 8 version, but if your project wants to use Java 11 you just need to add these below two lines in your bash script
        
```
export JAVA_HOME=/usr/lib/jvm/openjdk-11
export PATH=$JAVA_HOME/bin:$PATH
```

|Environment|	Platform|	AMI#|	Last Update Date	|Capabilities in-build|
|---|---|---|---|---|
|UAT/Dev|Linux|ami-053706a68d7863705|11 March 2021|docker -version 19.03.6<br>docker-compose -version 1.25.0<br>JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64<br>Open JDK 11= /usr/lib/jvm/openjdk-11<br>SDK<br>Node -v14.16.0, v12, v8<br>nvm- source /home/bamboo/.nvm/nvm.sh<br>Helm - 3.5.2<br>Ansible - 2.9.6<br>Terraform - 0.14.7<br>Packer - 1.7<br>aws cli - 1.19.14<br>Terragrunt<br>tfsec<br>tfswitch<br>jq 1.5-1<br>yq 4.6.0<br>aws credential helper<br>gpg<br>go version go1.11 linux/amd64<br>gosec<br>pkg<br>composer<br>Nexus IQ jar- /home/bamboo/nexus-iq-cli-1.106.0-01.jar|  
|Prod|Linux|ami-030031b9b267e32c9 (40GB)<br>ami-0333853a94c244e9e (20GB)|1 July 2021|docker -version 19.03.6<br>docker-compose -version 1.25<br>JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64<br>Open JDK 11= /usr/lib/jvm/openjdk-11<br>SDK<br>Node -v14.16.0, v12, v8<br>nvm- source /home/bamboo/.nvm/nvm.sh<br>Helm - 3.5.2<br>Ansible - 2.9.6<br>Terraform - 0.14.7<br>Packer - 1.7<br>aws cli - 1.19.14<br>Terragrunt<br>tfsec<br>tfswitch<br>jq 1.5-1<br>yq 4.6.0<br>aws credential helper<br>gpg<br>go version go1.11<br>go version go1.12.4 /home/bamboo/sdk/go1.12.4<br>go version go1.15.13 /home/bamboo/sdk/go1.15.13<br>go version go1.16.5 /home/bamboo/sdk/go1.16.5<br>gosec<br>pkg<br>composer<br>Nexus IQ jar- /home/bamboo/nexus-iq-cli-1.106.0-01.jar<br>bundler 2.1.4<br>rails 5.2.6<br>ruby 2.7 <br>yarn 1.22.10|
|Early Release|Linux|ami-01d05990da9319006 (40GB) - 21032022<br>To use this AMI in your test build, submit a ticket to us and request for this AMI to be attached to your plan. |21 March 2022|docker --version 20.10.12<br>docker-compose --version 1.29.2<br>docker-credential-ecr-login - /home/bamboo/amazon-ecr-credential-helper-main/bin/local<br>JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64<br>Open JDK 11= /usr/lib/jvm/openjdk-11<br>[SDK](https://sdkman.io/usage)<br>Node - v16.14.0, v14.18.1, v12, v10, v8<br>nvm- source /home/bamboo/.nvm/nvm.sh<br>kubectl - /home/bamboo/.local/bin/kubectl<br>k9s - /home/bamboo/.local/opt/k9s-v0.24.15/bin/k9s<br>Helm - 3.8.0<br>Ansible - 2.9.6<br>Terraform - 1.1.6 (switch from [tfswitch](https://tfswitch.warrensbox.com/Quick-Start/))<br>Packer - 1.7.10<br>Terragrunt<br>tfsec v1.4.2<br>tfswitch v0.13.1201 (tfswitch -b $HOME/bin/terraform 1.x.x )<br>jq 1.5-1<br>yq 4.6.0<br>aws credential helper<br>aws sam cli<br>gpg<br>go version go1.12.4 /user/bamboo/sdk/go1.12.4<br>go version go1.15.13 /user/bamboo/sdk/go1.15.13<br>go version go1.16.5 /user/bamboo/sdk/go1.16.5<br>go version go1.16.6 /user/bamboo/sdk/go1.16.6<br>go version go1.18 /user/bamboo/sdk/go.1.18/go<br>gosec<br>pkg<br>composer<br>Nexus IQ jar- /home/bamboo/nexus-iq-cli-1.133.0.jar<br>bundler 2.1.4<br>rails 5.2.6<br>ruby 2.7 <br>yarn 1.22.10<br>aws cli v2.4.21<br>[asdf multiple runtime manager](https://asdf-vm.com/guide/getting-started.html#_4-install-a-plugin)<br>checkov v2.0.917<br>SonarScanner v4.6.2<br>Python v3.9.10|


### Base Linux Agent Image Capabilities

**Executable:** *executable* capabilities define the executables which are available to your build plans.

|Executable Label<br>A label to uniquely identify this executable|Path<br>Please enter the path to your executable|  
|---|---|
Maven 2.1 (Maven 2.x)	|/opt/maven-2.1
Maven 2.2 (Maven 2.x)	|/opt/maven-2.2
Maven 3 (Maven 3.x)	|/opt/maven-3.5
Maven 3.2 (Maven 3.x)	|/opt/maven-3.2
Maven 3.3 (Maven 3.x)	|/opt/maven-3.3
Maven 3.5 (Maven 3.x)	|/opt/maven-3.5
Maven 3.6 (Maven 3.6.3)	|/opt/maven-3.6
Maven 3.8 (Maven 3.8.1)	|/opt/maven-3.8
Node.js 4 (Node.js)	|/opt/node-4/bin/node
Node.js 6 (Node.js)	|/opt/node-6/bin/node
Node.js 8 (Node.js)	|/opt/node-8/bin/node
PHPUnit 3.7 (PHPUnit)	|/opt/phpunit-3.7/phpunit
PHPUnit 4.4 (PHPUnit)	|/opt/phpunit-4.4/phpunit

**JDK:** JDK capabilities define the JDKs which are available to your build plans.

|JDK Label|Java Home|  
|---|---|
JDK 1.7	|/opt/jdk-7
JDK 1.8	|/opt/jdk-8
JDK 11	|/opt/jdk-11
JDK 17	|/opt/jdk-17

**Mercurial**
The path to the Mercurial executable (e.g. `C:\Program Files (x86)\Mercurial\hg.exe` or `/usr/local/bin/hg`)

|Executable|Path|  
|---|---|
Mercurial	|/usr/bin/hg

**Git**
The path to the Git executable (e.g. `C:\Program Files (x86)\Git\git.exe` or `/usr/local/git/bin/git`)

|Executable|Path|  
|---|---|
Git	|/usr/bin/git

**Docker**
The path to the Docker executable (e.g. `/usr/bin/docker`)

|Executable|Path|  
|---|---|
Docker	|/usr/bin/docker

**Terraform**
The path to the Terraform executable (e.g. `/usr/bin/terraform`)

|Executable|Path|  
|---|---|
Terraform	|/usr/bin/terraform

### Base HATS Windows Elastic Image (version 7.2.2 build 70209) source

|Environment|Platform|Visibility|AMI#|Latest Patch Level|Elastic Agent Version|
|---|---|---|---|---|---|  
|Dev / GCC Prod	|Windows|Private	|ami-076bf40ca91c570c2|March 2021|6.21|

### Base HATS Windows Agent Image Capabilities

|Executable Label|Path|  
|---|---|  
|Ant (Ant)|	C:\opt\ant-1.10
Ant 1.10 (Ant)	|C:\opt\ant-1.10
Ant 1.9 (Ant)	|C:\opt\ant-1.9
Dotnet Core 3.1 (Command)	|C:\Program Files\dotnet\dotnet.exe
Grails 2.4 (Grails)	|C:\opt\grails-2.4
Grails 3.2 (Grails)	|C:\opt\grails-3.2
Grails 3.3 (Grails)	|C:\opt\grails-3.3
MSBuild for Sonar Scanner Home (MSBuild)	|C:\opt\sonar-scanner-msbuild-4.6.2
MSBuild v15.0 (MSBuild)	|C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\MSBuild\15.0\bin\MSBuild.exe
MSBuild v16.0 (MSBuild)	|C:\Program Files (x86)\Microsoft Visual Studio\2019\Community\MSBuild\Current\Bin\amd64\MSBuild.exe
MSBuild v3.5 (MSBuild)	|C:\Windows\Microsoft.NET\Framework\v3.5\MSBuild.exe
MSBuild v4.0 (32bit) (MSBuild)	|C:\Windows\Microsoft.NET\Framework\v4.0.30319\MSBuild.exe
MSBuild v4.0 (64bit) (MSBuild)	|C:\Windows\Microsoft.NET\Framework64\v4.0.30319\MSBuild.exe
Maven 2 (Maven 2.x)	|C:\opt\maven-2.2
Maven 2.0 (Maven 2.x)	|C:\opt\maven-2.0
Maven 2.1 (Maven 2.x)	|C:\opt\maven-2.1
Maven 2.2 (Maven 2.x)	|C:\opt\maven-2.2
Maven 3 (Maven 3.x)	|C:\opt\maven-3.5
Maven 3.2 (Maven 3.x)	|C:\opt\maven-3.2
Maven 3.3 (Maven 3.x)	|C:\opt\maven-3.3
Maven 3.5 (Maven 3.x)	|C:\opt\maven-3.5
Maven 3.6 (Maven 3.x)	|C:\opt\maven-3.6
Nant (NAnt)	|C:\opt\nant-0.92
Node.js 4 (Node.js)	|C:\opt\node-4\node.exe
Node.js 6 (Node.js)	|C:\opt\node-6\node.exe
Node.js 8 (Node.js)	|C:\opt\node-8\node.exe
OpenCover (Command)	|C:\Program Files (x86)\OpenCover\OpenCover.Console.exe
PHPUnit 3.7 (PHPUnit)	|C:\opt\phpunit-3.7\phpunit.cmd
PHPUnit 4.4 (PHPUnit)	|C:\opt\phpunit-4.4\phpunit.cmd
Python 3.7.3 (Command)	|C:\Program Files\hats\Python37\python.exe
ReportGenerator (Command)	 |C:\Users\Bamboo\.dotnet\tools\ReportGenerator.exe
SCA Fortify Dotnet (Fortify SCA)	|C:\apps\fortify_latest\bin\sourceanalyzer.exe
Sonar Scanner Command for Windows (Command)	|C:\apps\sonar_latest\bin\sonar-scanner.bat
Sonar Scanner Dotnet (Sonar Scanner Home)	|C:\apps\sonar_latest
Sonar.MSBuild full path exe (MSBuild)	|C:\opt\sonar-scanner-msbuild-4.6.2\bin\SonarQube.Scanner.MSBuild.exe
VSTest Runner (VSTest Runner)	|C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\Common7\IDE\CommonExtensions\Microsoft\TestWindow\vstest.console.exe
nuget (Command)	|C:\opt\nuget\nuget.exe
sqlpackage (Command)	|C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\Common7\IDE\Extensions\Microsoft\SQLDB\DAC\130\sqlpackage.exe
vstest.console.exe (Command)	|C:\Program Files (x86)\Microsoft Visual Studio\2017\Community\Common7\IDE\CommonExtensions\Microsoft\TestWindow\vstest.console.exe


**JDK:** JDK capabilities define the JDKs which are available to your build plans.

|JDK|Label|  
|---|---|  
|JDK 1.8|C:\opt\jdk-8

**Agent environment capabilities:** Capabilities tied to the execution environment of the agent, like the operating system, architecture, network access.

|Capability|Value|  
|---|---|  
|EBS optimised|false
|EC2 Instance type|t3.2xlarge

**Mercurial:** The path to the Mercurial executable (e.g. `C:\Program Files (x86)\Mercurial\hg.exe` or `/usr/local/bin/hg`)

|Executable|Path|  
|---|---|  
|Mercurial|C:\opt\mercurial\hg.exe

**Git:** The path to the Git executable (e.g. `C:\Program Files (x86)\Git\git.exe` or `/usr/local/git/bin/git`)

|Executable|Path|  
|---|---|  
|Git|C:\opt\git\bin\git.exe|

### Base Windows Agent Package Versions

|Package|	Version|
|---|---|
|AWS CLI Version|	aws-cli/2.2.13 Python/3.8.8 Windows/10 exe/AMD64 prompt/off|
|Fortify SCA Version|	Fortify Static Code Analyzer 21.1.2.0002 (using JRE 11.0.10) Modules: SCA Platform 21.1.2.0002 MSBuild Plugin 21.1.2.0002 .NET and ASP.NET Translators 21.1.2.0001 COBOL Translator 83 C/C++ Translator (CTran) 21.1.0.0161 Go Translator 21.1.0.0061
|Java Version|	openjdk version "1.8.0_265" OpenJDK Runtime Environment Corretto-8.265.01.1 (build 1.8.0_265-b01) OpenJDK Server VM Corretto-8.265.01.1 (build 25.265-b01, mixed mode)
|msbuild|	Microsoft (R) Build Engine version 16.10.2+857e5a733 for .NET Framework Copyright (C) Microsoft Corporation. All rights reserved. 16.10.2.30804
|.NET Version|	5.0.301
|NPM Packages|	npm@6.14.4
|Nuget Version|	NuGet Version: 5.8.0.6930
|Python Version	|Python 3.7.3
|Sonar Scanner Version|	SonarScanner 4.6.1.2450 Java 11.0.3 AdoptOpenJDK (64-bit) Windows Server 2016 10.0 amd64

## Fair Usage Guidelines for Elastic Agents

This section documents the guidelines for all SHIP-HATS tenants to note when using bamboo elastic agents provided. Always refer to this page on latest updates.  

Behaviour when a build job is triggered:
- The build task will not start until an available elastic bamboo agent picks up the job.
- The build task will be processed on a first-come first-served basis.

As the bamboo elastic agents is a shared pool of resources and it is based on first-come first-served basis. In the event that the build/deployment is scheduled during peak period, it will be queued until the resource/agent is available to service the build jobs in the queue.  

While we strive to ensure consistent availability to all users, we would like to seek your co-operation to adhere to following guidelines.  

This will allow all tenants to have equal usage on the shared pool of bamboo elastic agents.   

(Dedicated bamboo agents are not in this scope)

### Fair Usage Policies

- Elastic bamboo agent jobs running more than 500 minutes continuously will be terminated to avoid impacting availability of the shared resources.
- Agencies with specific requirements could write in to enquires_SHIP@tech.gov.sg for evaluation by the SHIP team. Requests will be reviewed based on actual use-case. 
- Elastic bamboo agents should not be used to perform load testing. For agency that needs to conduct performance or load testing, please run the load test using own remote agent.
- Run jobs in your CI pipeline. Schedule jobs only when necessary, and during low peak hours. You could reach out to SHIP team to find out the recommended timing.

## Bamboo FAQs

- [Bamboo FAQs](https://docs.developer.tech.gov.sg/docs/ship-hats-documentation/#/tools-faq?id=bamboo-faq)