# Tools FAQ

This page covers Frequently Asked Questions [on tools integrated with SHIP-HATS](https://docs.developer.tech.gov.sg/docs/ship-hats-documentation/#/architecture-diagram).

# **Build**  **Tools FAQ**

SHIP-HATS has two tools used for the build component of the Continuous Integration/Continuous Deployment (CI/CD):

- Atlassian Bamboo
- Sonatype Nexus IQ and Sonatype Nexus Repository

## Bamboo FAQs

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

**Is it possible to install SHIP-HATS Bamboo agent on vendor&#39;s development servers for deployment and**  **testing****?**

No, however, vendor can set up a Remote Bamboo agent. For this option, the Agency would require to add-on Dedicated Remote Agent.

## About Bamboo Subscription

**How can I view the number of hours utilised by a Shared agent?**

Subscription Administrator (SA) and Project Administrator (PA) may connect to the SHIP-HATS OpenVPN and log in to [SHIP-HATS portal](http://www.ship.gov.sg/) to view the subscription&#39;s utilisation of Shared agent hours.

**How do I ensure the number of agent hours subscribed is sufficient for my system?**

Agency can monitor through [SHIP-HATS portal](http://www.ship.gov.sg/) after subscribing to the service platform. Agency can purchase additional Shared agent hours as add-ons based on project requirements.

**What happens if my project has maxed out the Shared agent hours?**

The SA and PA would receive an email notification when utilisation have reached 90% of the total number of Shared agent hours. Projects that exceed the Shared agent hours will be charged at 100 SGD per block of 100 Shareda Agent hours automatically. At the start of every month, the Shared Agent hours will be reset to its initial subscription quota.

**Will my Shared agent hours be rolled over to the next month if my project under utilised within the month?**

No. The number of Shared agent hours will reset on every 1st of the month.

