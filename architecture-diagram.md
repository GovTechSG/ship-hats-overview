# SHIP-HATS Architecture Diagram

**Commercially Off the Shelf (COTS)** tools are available on SHIP-HATS with the right security and compliance settings. The following diagram shows how they work together to provide a seamless platform. For more information on tools, refer to the [Tools in SHIP-HATS](#tools-in-ship-hats) section.

![ship archi](ship-archi.png)
>**Note:** The Release tools (Digital.ai Release and Digital.ai Deploy) that were included earlier in the SHIP-HATS platform have been discontinued. Existing Release tools users can continue to use these tools until migrated to new tools. 

## Terminology
The above diagram uses the following terminology:

| **Term** | **Description** |
| --- | --- |
| GSIB | Government Standard Image Build|
| GCC | Government Commercial Cloud |
| SOE | Standard ICT Operating Environment|
| VPC | Virtual Private Cloud|
| TWG | Transit Gateway|

<!--
- GSIB - Government Standard Image Build 
- SOE - Standard ICT Operating Environment 
- VPC - Virtual Private Cloud 
- TGW - Transit Gateway -->

## Tools in SHIP-HATS

<!-- ### Overview -->
 
The following section provide links to documentation and tutorials to learn the tools offered under **SHIP-HATS**. Note that these are not specific to SHIP-HATS but a pre-cursor to enable you to use these tools within SHIP-HATS effectively.  


| **Tool** | **Description** | **Links** |
| --- | --- | --- |
| **Jira** | Project management tool that is used to view, track, and manage projects and the progress of your team's tasks or bugs for a sprint displayed in an agile board. | [Overview](https://www.atlassian.com/software/jira/guides/getting-started/overview) & [Tutorials](https://www.atlassian.com/software/jira/guides/getting-started/basics#step-2-pick-a-template) | 
| **Confluence** | Shared space for collaboration to view, access, and manage all tasks and problems for the entire team enforces the idea of shared responsibility. Shared knowledge and environment also encourages experimentation. | [Overview](https://www.atlassian.com/software/confluence/guides/get-started/confluence-overview#hosting-options) & [Tutorials](https://www.atlassian.com/software/confluence/guides/get-started/set-up) | 
| **Bitbucket** | Version control tool for software engineering team to collaborate on source code and integrate with software development tools to automate the release pipeline. | [Overview](https://www.atlassian.com/software/bitbucket/guides/getting-started/overview) & [Tutorials](https://www.atlassian.com/software/bitbucket/guides/basics/bitbucket-interface#your-work) |

### Build Tool

| **Tool** | **Description** | **Link** |
| --- | --- | --- |  
| **Bamboo** | Tool for Continuous Integration that enables constant merging and testing of code, which leads to early defect detection and saves time to fix merge issues. This also enables the development teams to receive rapid feedback on their work. |  [Overview](https://www.atlassian.com/software/bamboo) |

### QA & Security Tools

| **Tool** | **Description** | **Links** |
| --- | --- | --- |
| **Nexus Repository Manager** | Tool for artifact management to ensure that the development, build, and production environments deploy consistent artifacts. This tool helps in reducing errors due to differences in build artifacts. This tool also provides version control for release artifacts for better control and easier rollback. | [Overview](https://www.sonatype.com/product-nexus-repository) |  
| **Nexus IQ** | Tool for scanning application binaries and open source libraries for all popular formats, including NPM, Nuget, Maven, Bowser, and more. This tool continuously monitors and alerts users of open-source vulnerabilities. | [Overview](https://www.sonatype.com/nexus-iq-server) |  
| **pCloudy Test Farm** | Tool to run automated tests on browsers (desktop and mobile) and mobile apps. Automation is triggered from Bamboo using the [Robot Framework](https://robotframework.org/). | [Overview](https://www.pcloudy.com/) |
| **SonarQube** | Automatic code review tool to detect bugs, vulnerabilities, and code smell. 15 supported base languages include C#, Java, CSS, VB.NET, JavaScript, XML, TypeScript, Python, Flex, Kotlin, PHP, Go, Ruby, HTML, and Scala. | [Overview](https://docs.sonarqube.org/latest/) |
| **Fortify WebInspect** | Dynamic Application Security Testing (DAST) tool that identifies vulnerabilities in web applications and APIs while they are running in production. | [Overview & Free Trial](https://www.microfocus.com/en-us/products/webinspect-dynamic-analysis-dast/overview) |  |
**Fortify SCA** | Static Application Security Testing (SAST) tool that identifies security vulnerabilities in software source code. Developers find and fix security defects in real-time during the coding process, with integrations to IDEs. | [Overview](https://www.microfocus.com/en-us/products/static-code-analysis-sast/overview) |  

<!--
| **Prisma Cloud Compute Edition (formerly TwistLock)** | A cloud native container vulnerability scanner that protects custom container images, configured by subscribers. | [Tutorials](https://docs.paloaltonetworks.com/prisma/prisma-cloud.html) |
-->
<!--
### Release Tools 

| **Tool** | **Description** | **Link** |
| --- | --- | --- |
| **Digital.ai Release** | Tool for release orchestration for continuous delivery. It enables teams across an organization to model and monitor releases, automate tasks within IT infrastructure, and reduce release times by optimising release processes. | [Overview](https://digital.ai/resources/release) |  
| **Digital.ai Deploy** | Tool for Automating App Deployment.  As software lifecycles continue to accelerate and deployment environments become numerous, error-free application deployments have become too complex to manage. Organizations need to automate and standardize app deployment. | [Overview](https://digital.ai/resources/deploy) | 
-->
<!--
### Development Tools

**Jira:** Project management tool that is used to view, track and manage projects and the progress of your team's tasks or bugs for a sprint displayed in an agile board.
[Overview](https://www.atlassian.com/software/jira/guides/getting-started/overview) | [Tutorials](https://www.atlassian.com/software/jira/guides/getting-started/basics#step-2-pick-a-template)

**Confluence:** Shared space for collaboration to view, access and manage all tasks and problems for the entire team enforces the idea of the shared responsibility. Knowledge sharing and environment also encourage experimentation.
[Overview](https://www.atlassian.com/software/confluence/guides/get-started/confluence-overview#hosting-options) | [Tutorials](https://www.atlassian.com/software/confluence/guides/get-started/set-up)

**Bitbucket:** Version control tool for software engineering team to collaborate on source code and integrate with software development tools to automate the release pipeline.
[Overview](https://www.atlassian.com/software/bitbucket/guides/getting-started/overview) | [Tutorials](https://www.atlassian.com/software/bitbucket/guides/basics/bitbucket-interface#your-work)

### Build Tool

**Bamboo:** Tool for Continuous Integration that allows constant merging and testing of code, which leads to early defect detection and saves time on fixing merge issues. Development teams also able receive rapid feedback on their work. [Overview](https://www.atlassian.com/software/bamboo)

### QA & Security Tools

**Nexus Repository Manager:** Tool for artifact management to ensure that the development, build and production environments deploy consistent artifacts; Reduce errors due to differences in build artifacts. Version control for the release artifacts for better control and easier rollback. [Overview](https://www.sonatype.com/product-nexus-repository)

**Nexus IQ:** Tool for scanning application binaries and open source libraries for all popular formats, including NPM, Nuget, Maven, Bowser and more. Continuously monitors and alerts users of open-source vulnerabilities [Overview](https://www.sonatype.com/nexus-iq-server)

**pCloudy Test Farm:** Tool to execute automated tests on browsers (desktop, mobile) and mobile apps. Automation is triggered from Bamboo using [Robot Framework](https://robotframework.org/). [Overview](https://www.pcloudy.com/)

**SonarQube:** Automatic code review tool to detect bugs, vulnerabilities, and code smell. 15 base languages include C#, Java, CSS, VB.NET, JavaScript, XML, TypeScript, Python, Flex, Kotlin, PHP, Go, Ruby, HTML, Scala. [Overview](https://docs.sonarqube.org/latest/)

**Fortify WebInspect:** Dynamic Application Security Testing (DAST) tool that identifies vulnerabilities in web applications and APIs while they are running in production. [Overview & Free Trial](https://www.microfocus.com/en-us/products/webinspect-dynamic-analysis-dast/overview)

**Fortify SCA:** Static Application Security Testing (SAST) tool that identifies security vulnerabilities in software source code. Developers find and fix security defects in real-time during the coding process, with integrations to IDEs. [Overview](https://www.microfocus.com/en-us/products/static-code-analysis-sast/overview)

**Prisma Cloud Compute Edition (formerly TwistLock):** A cloud native container vulnerability scanner that protects custom container images, configured by subscribers. [Tutorials](https://docs.paloaltonetworks.com/prisma/prisma-cloud.html)

### Release Tools 


**Digital.ai Release:** Tool for release orchestration for continuous delivery. It enables teams across an organization to model and monitor releases, automate tasks within IT infrastructure, and cut release times by optimising release processes. [Overview](https://digital.ai/resources/release) 
  

**Digital.ai Deploy:** Tool for Automating App Deployment.  As software lifecycles continue to accelerate and deployment environments become numerous, error-free application deployments have become too complex to manage. Organizations need to automate and standardize. [Overview](https://digital.ai/resources/deploy) 

 -->

