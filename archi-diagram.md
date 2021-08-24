# SHIP-HATS Architecture Diagram

![ship archi](ship-archi.png)

- GSIB - Government Standard Image Build 
- SOE - Standard ICT Operating Environment 
- VPC - Virtual Private Cloud 
- TGW - Transit Gateway 

## Tools in SHIP-HATS

### Overview
 
**Commercially Off the Shelf (COTS)** tools are available on SHIP-HATS with right security and compliance settings. Here are curated links to documentation and tutorials to first learn the tools offered under **SHIP-HATS**. Note this is not specific to SHIP-HATS but a pre-cursor so you can use these tools within SHIP-HATS effectively.  

### Development Tools

**Jira:** Project management tool that is used to view, track and manage projects and the progress of your team's tasks or bugs for a sprint displayed in an agile board.
[Overview](https://www.atlassian.com/software/jira/guides/getting-started/overview) | [Tutorials](https://www.atlassian.com/software/jira/guides/getting-started/basics#step-2-pick-a-template)

**Confluence:** Shared space for collaboration to view, access and manage all tasks and problems for the entire team enforces the idea of the shared responsibility. Knowledge sharing and environment also encourage experimentation.
[Overview](https://www.atlassian.com/software/confluence/guides/get-started/confluence-overview#hosting-options){:target="_blank"} | [Tutorials](https://www.atlassian.com/software/confluence/guides/get-started/set-up){:target="_blank"}

**Bitbucket:** Version control tool for software engineering team to collaborate on source code and integrate with software development tools to automate the release pipeline.
[Overview](https://www.atlassian.com/software/bitbucket/guides/getting-started/overview){:target="_blank"} | [Tutorials](https://www.atlassian.com/software/bitbucket/guides/basics/bitbucket-interface#your-work){:target="_blank"}

### Build Tool

**Bamboo:** Tool for Continuous Integration that allows constant merging and testing of code, which leads to early defect detection and saves time on fixing merge issues. Development teams also able receive rapid feedback on their work. [Overview](https://www.atlassian.com/software/bamboo){:target="_blank"}

### QA & Security Tools

**Nexus Repository Manager:** Tool for artifact management to ensure that the development, build and production environments deploy consistent artifacts; Reduce errors due to differences in build artifacts. Version control for the release artifacts for better control and easier rollback. [Overview](https://www.sonatype.com/product-nexus-repository){:target="_blank"}

**Nexus IQ:** Tool for scanning application binaries and open source libraries for all popular formats, including NPM, Nuget, Maven, Bowser and more. Continuously monitors and alerts users of open-source vulnerabilities [Overview](https://www.sonatype.com/nexus-iq-server){:target="_blank"}

**pCloudy Test Farm:** Tool to execute automated tests on browsers (desktop, mobile) and mobile apps. Automation is triggered from Bamboo using [Robot Framework](https://robotframework.org/){:target="_blank"}. [Overview](https://www.pcloudy.com/){:target="_blank"}

**SonarQube:** Automatic code review tool to detect bugs, vulnerabilities, and code smell. 15 base languages include C#, Java, CSS, VB.NET, JavaScript, XML, TypeScript, Python, Flex, Kotlin, PHP, Go, Ruby, HTML, Scala. [Overview](https://docs.sonarqube.org/latest/){:target="_blank"}

**Fortify WebInspect:** Dynamic Application Security Testing (DAST) tool that identifies vulnerabilities in web applications and APIs while they are running in production. [Overview & Free Trial](https://www.microfocus.com/en-us/products/webinspect-dynamic-analysis-dast/overview){:target="_blank"}

**Fortify SCA:** Static Application Security Testing (SAST) tool that identifies security vulnerabilities in software source code. Developers find and fix security defects in real-time during the coding process, with integrations to IDEs. [Overview](https://www.microfocus.com/en-us/products/static-code-analysis-sast/overview){:target="_blank"}

**Prisma Cloud Compute Edition (formerly TwistLock):** A cloud native container vulnerability scanner that protects custom container images, configured by subscribers. [Tutorials](https://docs.paloaltonetworks.com/prisma/prisma-cloud.html){:target="_blank"}

### Release Tools

**Digital.ai Release:** Tool for release orchestration for continuous delivery. It enables teams across an organization to model and monitor releases, automate tasks within IT infrastructure, and cut release times by optimising release processes. [Overview](https://digital.ai/resources/release){:target="_blank"}

**Digital.ai Deploy:** Tool for Automating App Deployment.  As software lifecycles continue to accelerate and deployment environments become numerous, error-free application deployments have become too complex to manage. Organizations need to automate and standardize. [Overview](https://digital.ai/resources/deploy){:target="_blank"}

