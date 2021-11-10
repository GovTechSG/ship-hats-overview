# Tools FAQ

This page covers Frequently Asked Questions [on tools integrated with SHIP-HATS](https://docs.developer.tech.gov.sg/docs/ship-hats-documentation/#/architecture-diagram).

- [Build Tools FAQ](build-tools-faq)
- [QA and Security Tools FAQ](qa-and-security-tools-faq)

# [Build Tools FAQ](#build-tools-faq)

SHIP-HATS has two tools used for the build component of the Continuous Integration/Continuous Deployment (CI/CD): 
- [Atlassian Bamboo](bamboo-faq)
- Sonatype Nexus IQ and [Sonatype Nexus Repository](sonatype-nexus-repository-faq)

## [Bamboo FAQs](#bamboo-faq)

**What is a Bamboo agent?**

A Bamboo agent is a service that allows to run job builds. There are different types of agents: remote, shared, local and elastic agents. For more information on agents, refer to [Agents and Capabilities on Atlassian.](https://confluence.atlassian.com/bamboo/agents-and-capabilities-289277114.html)

**Can I use a Remote agent?**

A <a href="https://confluence.atlassian.com/confeval/development-tools-evaluator-resources/bamboo/bamboo-remote-agents-and-local-agents">Remote agent</a> requires hosting, agent installation and/or VPN installation (if required). Registration of Remote agent is subjected to approval by SHIP-HATS team. Please send a service request via SHIP-HATS service desk for registration of Remote Agent

**When does my project require a Dedicated Remote agent?**

If your build job needs to connect back to your own resources or run parallel job, you can consider adding a Dedicated Remote agent.For more information, refer to [dedicating an agent](https://confluence.atlassian.com/bamboo/dedicating-an-agent-629015108.html).

**What is the requirement for Remote agents?**
Agency must ensure the Remote agents are clean and secure before SHIP-HATS approves the registration with Bamboo server.

To setup Remote Bamboo agents, please refer to this [guide](https://confluence.ship.gov.sg/display/SHIP/Installing+Remote+Agent). This page is on SHIP-HATS confluence. Please log in to the account to access.

To ensure that Remote agents are clean and secure, refer to [securing your Remote agents](https://confluence.atlassian.com/bamboo/securing-your-remote-agents-289277197.html). This page is on SHIP-HATS confluence. Please log in to the account to access.

**What is a Shared Elastic agent?**

A Shared Elastic agent is an on-demand Windows or Linux agent launched by Bamboo within SHIP&#39;s network to execute pipeline tasks. To leverage on elastic agent, Agency must specify the required capabilities and SHIP-HATS team will assign an agent that matches the required capabilities, if available.

SHIP-HATS does not offer Mac OS Agent as of now.

For more information on specifying required capabilities, refer to [Bamboo agent registration process](https://confluence.ship.gov.sg/display/SHIP/Bamboo+Agent+Registration+Process). This page is on SHIP-HATS confluence. Please log in to the account to access.

**Which OS is available for the shared elastic agent?**
Though MS Windows and Linux support, we recommend Linux as MS Window agents are quite heavy and would utilise a hefty load of Shared Agent hours. We recommend the Agency subscribe to Remote Agent if they choose MS Window agents.

**What tools are already installed on the Shared agents?**

Refer to [SHIP Bamboo Elastic Agent for SHIP Users.](https://confluence.ship.gov.sg/display/SHIP/SHIP+Bamboo+Elastic+Agent+for+SHIP+Users) This page is on SHIP-HATS confluence. Please log in to the account to access.

**What if I require a specific tool on the Shared agent?**

Submit your requests <a href="https://go.gov.sg/she"> here.</a>

**Is it possible to install SHIP-HATS Bamboo agent on vendor&#39;s development servers for deployment and testing?**

No, however, vendor can set up a Remote Bamboo agent. For this option, the Agency would require to add-on Dedicated Remote Agent.

### About Bamboo Subscription

**How can I view the number of hours utilised by a Shared agent?**

Subscription Administrator (SA) and Project Administrator (PA) may connect to the SHIP-HATS OpenVPN and log in to [SHIP-HATS portal](http://www.ship.gov.sg/) to view the subscription&#39;s utilisation of Shared agent hours.

**How do I ensure the number of agent hours subscribed is sufficient for my system?**

Agency can monitor through [SHIP-HATS portal](http://www.ship.gov.sg/) after subscribing to the service platform. Agency can purchase additional Shared agent hours as add-ons based on project requirements.

**What happens if my project has maxed out the Shared agent hours?**

The SA and PA would receive an email notification when utilisation have reached 90% of the total number of Shared agent hours. Projects that exceed the Shared agent hours will be charged at 100 SGD per block of 100 Shareda Agent hours automatically. At the start of every month, the Shared Agent hours will be reset to its initial subscription quota.

**Will my Shared agent hours be rolled over to the next month if my project under utilised within the month?**

No. The number of Shared agent hours will reset on every 1st of the month.

## [Sonatype Nexus Repository FAQ](#sonatype-nexus-repository-faq)

**I want to use Nexus Repository in my project to publish custom libraries for the developers in my team to use. Is it possible?**

SHIP-HATS users can request to create a private hosted repository in Nexus Repository to host their custom libraries by raising a [service request](https://jira.ship.gov.sg/servicedesk/customer/portal/11). 

**Is it possible to use Nexus repository in SHIP-HATS as a proxy to the central repository?**

Yes, it is possible to use Nexus Repository in SHIP-HATS as proxy to the central repository. 

**What is the archival policy for Nexus Repository?**

All Artifacts will be deleted 180 days from the date of creation. 

# [QA and Security Tools FAQ](#qa-and-security-tools-faq)

SHIP-HATS has a list of tools used for the Quality assurance (QA) and Security components of the Continuous Integration/Continuous Deployment (CI/CD): 

- [Test Farm](test-farm) 
- [SonarQube](sonarqube) 

## [Test Farm](#test-farm) 

**What is a shared Test Farm?**

It is a cloud-based mobile devices test platform which allows testing of Android and iOS mobile applications or mobile browsers on real device. It allows the user to run test automation on multiple devices in parallel. Since it is a shared Test Farm, your test will be added to a queue system if all the resources are not available at the time of request.Refer [here](https://sgdcs.sgnet.gov.sg/sites/tech/hats/SitePages/Green%20HATS.aspx) for the automated testing framework supported.  

**What test automation frameworks are supported by the Test Farm?**

SHIP-HATS support [Appium](https://appium.io/) based open source framework like [Robot Framework](https://robotframework.org/) and  any other testing frameworks that can work with Appium server.  

**What type of applications can use the Test Farm?**

Any internet or intranet facing application that can be exposed to the internet for testing can use the Test Farm. 

**Can I choose the devices in the Shared Test Farm?**
Users can pre-book the mobile devices based on OS, brand or model before running their tests by sending an enquiry to enquiries_ENP@tech.gov.sg. The number of devices that agency can book depends on their subscription quota. The test will be executed on the booked mobile devices that agency specifies. 

**When do I purchase a Dedicated iOS or Android add-on?**

If you wish to avoid queueing, you can subscribe to Dedicated iOS and Android add-on. Public officers can refer to the [pricing](https://sgdcs.sgnet.gov.sg/sites/IDA-GoSync/gdspdd-ai/ship/_layouts/15/start.aspx#/SitePages/Pricing.aspx). 

**How do I provision the mobile and desktop browser Test Farm?**

Agencies are required to raise a [service request](https://jira.ship.gov.sg/servicedesk/customer/portal/11) to request access to the Test Farm. 

## [SonarQube](#sonarqube) 

**What are the 15 supported languages?**

Java, JavaScript, C#, TypeScript, Kotlin, Ruby, Go, Scala, Flex, Python, PHP, HTML, CSS, XML, VB.NET. 
Do take note that there is no restriction of lines of code and number of applications. 

**Based on SonarQube’s add-ons, what are the 7 others supported languages?**

C, C++, Obj-C, Swift, ABAP, T-SQL, PL/SQL are supported. Public officers can refer to the [pricing](https://sgdcs.sgnet.gov.sg/sites/IDA-GoSync/gdspdd-ai/ship/_layouts/15/start.aspx#/SitePages/Pricing.aspx) for the add-ons.  

**Are COTS (commercial off-the-shelf) products supported on SonarQube?**

Yes. SonarQube can scan for any customisation that the COTS product supports.       
Example: Configuration files in XML or Javascript/ Java or plugins written in Java or Python 
