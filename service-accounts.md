# Service Accounts

To interact with your HATS applications in your CI/CD pipelines, we recommend following options:
- [Using Auto-generated Token from SHIP-HATS Portal](#auto-generated-token)
- [Using SHIP LDAP Service Account](#ship-ldap-service-account)

## Auto-generated Token

### Use auto-generated token from SHIP-HATS portal:
- If you do not want to manage your own service accounts and tokens 

In the [SHIP-HATS portal](https://www.ship.gov.sg/), we manage local service account for each project. This account has permission to perform CI/CD. You would be required to log in to the portal and retrieve the token from it. For more information on how to retrieve the token, refer to the corresponding section in respective tool area in [the Tools documentation](tools-overview). 

### Who can do it? 
Project Admins can retrieve the tokens.

### Username format 
svc-acct-`<your-project-name>`

### Why should you use this method?

- When you create the service account via the [SHIP-HATS portal](https://www.ship.gov.sg/), this local service account is automatically added to your applications. 
- You require these accounts to pull data for [Thinking HATS](https://thinking.hats.stack.gov.sg/) (Consolidated quality dashboard and reporting). 
- Using this service account, you will be able to pull data and statistics from your Fortify/Sonarqube application, and view these trends and statistics in Thinking Hats.

## SHIP LDAP Service Account

### Use SHIP LDAP service account:

- If you want to control/manage token generation 
- If you want to unify single service account for all the SHIP and HATS tools 

The Service account is also a user account which will have its email id, but it will be shared with the team.

### Who can do it?
Project Admin or Subscriber admin must create the user in the [SHIP-HATS portal](https://www.ship.gov.sg/).

### To use SHIP LDAP service account:
1. Create Service account. 
1. Add new user. 
    - Fortify
        - [Add users to the Fortify App on SSC](https://docs.developer.tech.gov.sg/docs/ship-hats-documentation/#/manage-fortify-applications?id=add-users-to-fortify-applications) 
        - [Manage Token](https://docs.developer.tech.gov.sg/docs/ship-hats-documentation/#/fortify-manage-user-tokens)
    - Sonar
        - [Add users](https://docs.developer.tech.gov.sg/docs/ship-hats-documentation/#/sonarqube-self-help-guide?id=manage-users)
