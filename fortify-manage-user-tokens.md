# Manage Fortify User Tokens

There might be instances where users want to create their own token for testing purposes using their own credentials. The following topics provide information on how to manage user tokens.

**Topics**
- [Create a User Token](#create-a-user-token)
- [Delete/Invalidate a User Token](#deleteinvalidate-a-user-token)

## Create a User Token
### To create a user token using Web UI:

1. Log in to the [Fortify website](https://ssc.hats.stack.gov.sg/ssc).
1. Click **Administration** > **Users** > **Token Management**. 
    ![Token management](hats-fortify-token-management-admin.png)
1. Click **New**.
    ![New token](hats-fortify-token-management-new.png)
1. Enter values in the followig fields, and then click **Save**.
    - **Token Type**
    - **Description**
1. After you click **Save**, the encoded and decoded tokens are shown once. Copy the Decoded token and use it for your bamboo plan.
    ![Decoded token](fortify-decoded-token.png)

### To create a user token using fortifyclient:

**token crate**
```
fortifyclient -url https://ssc.hats.stack.gov.sg/ssc token -gettoken UnifiedLoginToken -user $USER -password $PASSWORD -daysToLive 1
```

## Delete/Invalidate a User Token
### To delete/invalidate a user token using Web UI:

1. Log in to the [Fortify website](https://ssc.hats.stack.gov.sg/ssc).
1. Click **Administration** > **Users** > **Token Management**. 
    ![Token management Delete](hats-fortify-token-management-delete.png)
1. Select the token you need to invalidate, and press **Delete**.

### To delete/invalidate a user token using fortifyclient:

**token delete**
```
fortifyclient -url https://ssc.hats.stack.gov.sg/ssc invalidatetoken -invalidate $token -user $USER -password $PASSWORD
```