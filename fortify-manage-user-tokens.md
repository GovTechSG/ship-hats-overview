# Manage Fortify User Tokens

There might be instances where users want to create their own token for testing purposes using their own credentials. The following topics provide information on how to manage user tokens.

**Topics**
- [Create a User Token](#create-a-user-token)
- [Delete/Invalidate a User Token](#deleteinvalidate-a-user-token)

## Create a User Token
### To create a user token using Web UI:

1. Log in to the Fortify website (https://ssc.hats.stack.gov.sg/ssc)
1. Visit "Token Management" Under Administration - > Users
https://ssc.hats.stack.gov.sg/ssc/html/ssc/admin/tokens
1. Select "New"
1. Upon clicking Save, the encoded and decoded tokens are shown once, please copy the Decoded token and use it for your bamboo plan.

### To create a user token using fortifyclient:

**token crate**
```
fortifyclient -url https://ssc.hats.stack.gov.sg/ssc token -gettoken UnifiedLoginToken -user $USER -password $PASSWORD -daysToLive 1
```

## Delete/Invalidate a User Token
### To delete/Invalidate a user token using Web UI:

1. Log in to the Fortify website (https://ssc.hats.stack.gov.sg/ssc)
1. Visit "Token Management" Under Administration - > Users
1. Select the token you need to invalidate and press "Delete"

### To delete/Invalidate a user token using fortifyclient:

**token delete**
```
fortifyclient -url https://ssc.hats.stack.gov.sg/ssc invalidatetoken -invalidate $token -user $USER -password $PASSWORD
```