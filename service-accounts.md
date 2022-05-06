# Service Accounts

To interact with your HATS applications in your CI/CD pipelines we recommend following options.
- [Using Auto-generated Token from SHIP-HATS Portal](#using-auto-generated-token-from-ship-hats-portal)
- [Using SHIP LDAP Service Account](#using-ship-ldap-service-account)

## Using Auto-generated Token from SHIP-HATS Portal

If you do not want to manage your own service accounts and tokens, this would be the most convenient way to manage your service account. 

In [SHIP-HATS portal](https://www.ship.gov.sg/), we manage local service account for each project. This account has permission to perform CI/CD. You would be required to login to the portal and retrieve the required token from it.

How : Token Management for Hats Services

### Who can do it? 
Project Admins can retrieve the tokens.

### Username format 
svc-acct-<\your-project-name>

### Why should you use this method?

- This local service account is automatically added to your applications when you create it via the [SHIP-HATS portal](https://www.ship.gov.sg/). 
- These accounts are used to pull data for Thinking HATS(Consolidated quality dashboard and reporting). 
- It will pull data and statistics from your Fortify/Sonarqube application, and display these trends and statistics in Thinking Hats itself.

## Using SHIP LDAP Service Account

Use this method:
- If you want to control/manage token generation 
- If you want to unify single service account for all the SHIP and HATS tools. 

The Service account is also a user account which will have its email id, but it will be shared with the team.

How :

1. Create Service account 
1. Add new User 
Fortify
Add users : Self-help: How to add users to Fortify App on SSC
Manage Token : Self-help: Managing Fortify user tokens
Sonar
Add users : Self-Help: How to manage users to SonarQube app for Project Admins


Who :  Project Admin or Subscriber admin has to create the user in Portal





