# Bamboo Elastic Agents - Fair Usage Guidelines

This page documents the guidelines for all SHIP-HATS tenants to note when using bamboo elastic agents provided. Always refer to this page on latest updates.  

Behaviour when a build job is triggered:
- The build task will not start until an available elastic bamboo agent picks up the job.
- The build task will be processed on a first-come first-served basis.

As the bamboo elastic agents is a shared pool of resources and it is based on first-come first-served basis. In the event that the build/deployment is scheduled during peak period, it will be queued until the resource/agent is available to service the build jobs in the queue.  

While we strive to ensure consistent availability to all users, we would like to seek your co-operation to adhere to following guidelines.  

This will allow all tenants to have equal usage on the shared pool of bamboo elastic agents.   

(Dedicated bamboo agents are not in this scope)

## Fair Usage Policies

1. Elastic bamboo agent jobs running more than 500 minutes continuously will be terminated to avoid impacting availability of the shared resources.
1. Agencies with specific requirements could write in to enquires_SHIP@tech.gov.sg for evaluation by the SHIP team. Requests will be reviewed based on actual use-case. 
1. Elastic bamboo agents should not be used to perform load testing. For agency that needs to conduct performance or load testing, please run the load test using own remote agent.
1. Run jobs in your CI pipeline. Schedule jobs only when necessary, and during low peak hours. You could reach out to SHIP team to find out the recommended timing.

## Create Elastic Agent

### Prerequisites

- Subscription Admin (SA), Project Admin (PA), Developers
- 
1.	**Provision for Bamboo Remote Agent:** Bamboo Remote Agent is an add-on tool, which is not part of the standard subscription. Do check if you have a sufficient quota of bamboo agents subscribed. If there are none subscribed/insufficient quota, SA will need to subscribe/increase the quota by raising a [service request](https://jira.ship.gov.sg/servicedesk/customer/portal/11) ticket. 
1.	**VPC Endpoint Setup:** Applicable for setting up an agent in AWS, you can leverage VPC endpoints to connect to VPC endpoint services provided by SHIP.  
    1.	Create VPC endpoints for SHIP's endpoint services in the same VPC as the DevOps zone 
        1.	Bamboo and Bamboo Broker endpoints services are required to register Bamboo agents
        1.	Bitbucket and Bitbucket endpoint services is required to check out configuration and deployment scripts
    1.	Refer to SHIP AWS VPC Endpoint Connections
1.	**Machine VPN Setup:** Applicable for setting up an agent outside AWS (e.g. Azure) or if you cannot leverage VPC endpoints to connect to VPC endpoint services provided by SHIP.   
    1.	Submit a [service request](https://jira.ship.gov.sg/servicedesk/customer/portal/11) to SHIP for OpenVPN Client config file for the Bamboo agent. This config file should not require password authentication. 
    2.	[Install OpenVPN client](https://openvpn.net/vpn-server-resources/how-to-connect-to-access-server-from-a-linux-computer/). 
1.	When Remote Agent had been provisioned, you may proceed to install the remote agent. Refer to Installing Remote Agent

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

## Bamboo FAQs
- [Bamboo FAQs](https://docs.developer.tech.gov.sg/docs/ship-hats-documentation/#/tools-faq?id=bamboo-faq)

## Register an Elastic Agent

### To register and elastic agent:
1.	The SHIP Bamboo golden image is configured to have the required capabilities (as shown below). We highly recommend using SHIP Bamboo Base Image as it will reduce the effort to test and build your own image and this image is constantly enhanced and scanned to ensure no security vulnerabilities. 
2.	Agencies having specific requirements could reach out to SHIP team to request for software that is not available in the base AMI.
3.	For those with exception and need to configure the elastic agent by themselves, after consulting SHIP team, following AMI could be used by launching the instance and configuring required softwares. 
4.	Once the softwares are installed, please create the image and share the image to SHIP GCC account (726262972162).  Please make sure that the root volume is having the setting "Delete on termination"  when you are creating the AMI. 
5.	If you already have a snapshot pre-prepared, then simply share the image to us.
6.	Please make sure that the "Add 'create volume' permission to the following associated snapshots when creating permissions" is selected when you share the AMI with SHIP  
    
    <kbd>![Modify Image Permissions]()

7.	Please raise a Service Desk ticket for adding this image to your agent. We will then scan the image and if there is no vulnerabilities we will update the AMI to your agent. If there is vulnerability issue, we will let you know and you have to fix it and share it back to us..
8.	Please note that we will keep updating our base image whenever we upgrade our bamboo server or if we get notified for any security vulnerability issues. Please follow this page so that you will be notified on this. 

## Base Elastic Agent AMI

### The base Linux elastic image for SHIP Bamboo (version 6.10.4 build 61009)
|Environment|	Platform|	AMI#|	Last Update Date	|Capabilities in-build|
|---|---|---|---|---|
|Prod/UAT/Dev|	Linux 	|ami-0f6e0e0d27bb8700d|	 27 Feb 2021|docker -version 19.03.6<br><br>docker-compose -version 1.25.0<br><br>Node v8.10.0<br><br>JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64<br><br>JAVA -version 1.8.0_282|

### The base Windows elastic image for SHIP Bamboo (version 6.10.4 build 61009)

>**Note:** We have encountered users having difficulty accessing the ec2 instances based of these ami. Please use Large instance sizes for optimal performance.

|Environment|Platform|Netcore|AMI#|	AWS Visibility|Latest Patch Level|Elastic Agent Version|
|---|---|---|---|---|---|---|
|Dev / GCC Prod|Windows|Netcore 31 MSbuild 16|ami-0b630d54d62dae335 (13-04-2022)<br><br>ami-080c9eadfa32623af (04-04-2022)<br><br>ami-0654a797b21f3b2fe (17-02-2022) <br><br>ami-0da6744c404a4eb49 (14-12-2021)|Public|Apr-2022|6.21|
|Dev / GCC Prod|Windows|Netcore 22 MSbuild 15|ami-0e96e48f2f267c7c9 (13-04-2022)<br><br>ami-09589f812ce820c6b (04-04-2022)<br><br>ami-08045c912e58aa213 (17-02-2022) <br><br>ami-0df3811b1877e9cd3 (14-12-2021)|Public|Apr-2022|6.21|

### The base Linux elastic image for SHIP Bamboo (version 7.2.2):

Please update your plans to match with the path stated below. Since we have multiple version of softwares installed , it is always good to check the version of the software set default and update your script to the version you require. For ex. we have Java 8 and 11 installed in our SHIP AMI and by default the JAVA_HOME points to Java 8 version, but if your project wants to use Java 11 you just need to add these below two lines in your bash script
        
```
export JAVA_HOME=/usr/lib/jvm/openjdk-11
export PATH=$JAVA_HOME/bin:$PATH
```

|Environment|	Platform|	AMI#|	Last Update Date	|Capabilities in-build|
|---|---|---|---|---|
|Prod/UAT/Dev|	Linux 	|ami-0f6e0e0d27bb8700d|	 27 Feb 2021|docker -version 19.03.6<br><br>docker-compose -version 1.25.0<br><br>Node v8.10.0<br><br>JAVA_HOME=/usr/lib/jvm/java-8-openjdk-amd64<br><br>JAVA -version 1.8.0_282|

### The Base Linux Agent Image will have the following capabilities defined:

**Executable:** executable capabilities define the executables which are available to your build plans.


**JDK:** JDK capabilities define the JDKs which are available to your build plans.

**Mercurial**
The path to the Mercurial executable (e.g. 'C:\Program Files (x86)\Mercurial\hg.exe' or '/usr/local/bin/hg')


**Git**
The path to the Git executable (e.g. 'C:\Program Files (x86)\Git\git.exe' or '/usr/local/git/bin/git')

**Docker**
The path to the Docker executable (e.g. '/usr/bin/docker')

**Terraform**
The path to the Terraform executable (e.g. '/usr/bin/terraform')

### The base HATS Windows elastic image for SHIP Bamboo (version 7.2.2 build 70209) source:

### The Base HATS Windows Agent Image will have the following capabilities defined:

**JDK:** JDK capabilities define the JDKs which are available to your build plans.
JDK label	Java home
JDK 1.8
C:\opt\jdk-8

**Agent environment capabilities:** Capabilities tied to the execution environment of the agent, like the operating system, architecture, network access.
Capability	Value
EBS optimised
false
EC2 Instance type
t3.2xlarge

**Mercurial:** The path to the Mercurial executable (e.g. 'C:\Program Files (x86)\Mercurial\hg.exe' or '/usr/local/bin/hg')
Executable	Path
Mercurial
C:\opt\mercurial\hg.exe

**Git:** The path to the Git executable (e.g. 'C:\Program Files (x86)\Git\git.exe' or '/usr/local/git/bin/git')
Executable	Path
Git
C:\opt\git\bin\git.exe

### The Base Windows Agent Package Versions

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
