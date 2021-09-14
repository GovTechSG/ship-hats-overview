# Logging In and Logging Out

**Prerequisites**:

- Before you start, you must have been invited and onboarded to SHIP-HATS.
- Once you have successfully onboarded, make sure that you have setup your OpenVPN connection.

## Logging In
Once the above are successfully completed, you can proceed to log in to SHIP-HATS. Logging in tells the system who you are and what permissions you have in SHIP-HATS. For example, if you are a Subscription Admin or Project Admin, you can view the SHIP-HATS [**Dashboard**](#viewing-dashboard) view once you log in. Other “Users” will be directed to their [**Profile**](#viewing-profile-as-users) page.

**Note:**

 - If you are the SA or PA for a subscription account and when you log in, by default, you will be viewing the subscription details of the first account to which you were added as SA or PA.

 - SA and PA must log in to SonarQube before proceeding to create applications in SonarQube. Though only SA and PA can create applications in SonarQube, we recommend all users to log in to SonarQube at least once to ease the process if a user role is changed to a PA role in the future.

Refer to [**Switch account**](#switch-account) to know how to switch between different subscription accounts.


*To log in to SHIP-HATS:*

1. Go to [SHIP-HATS portal](https://www.ship.gov.sg/).
2. Click **Log In**.

<kbd>![log-in](images/log-in.png ':size=100%')</kbd>

3. Enter your **Username** ,**Password** and click **Log In**.

## [Viewing Dashboard](#viewing-dashboard)
The **Overview** page of the subscription account gives the dashboard view of the subscription account. Only Subscription Admin (SA) and Project Admin (PA) can access this dashboard to view the following details.

- Subscription tier for the Billing Account
- [Plan details](https://docs.developer.gov.sg/docs/ship-hats-documentation/#/portal-guide/account-management/account-management?id=viewing-plan-details)
- Count of projects hosted on this account
- Count of users added to this account
- Projects using shared Bamboo agents and their usage quota.

?> Note: The term **Overview** and **Dashboard view** may be used interchangeably.



<kbd>![overview](images/overview-3.png ':size=100%')</kbd>

## [Viewing Profile as Users](#viewing-profile-as-users)
When users other than SA or PA log in to [SHIP-HATS portal](https://www.ship.gov.sg/), they are directed to their **Profile** page. You may view the details of the subsvription account under which your SHIP-HATS usage is currently billed.

<kbd>![profile-of-other-users](images/profile-of-other-users.png ':size=100%')</kbd>

## Logging Out
When you are done with your activities on the portal, you can log out as shown below.


*To log out from SHIP-HATS:*

- Hover over your profile icon and click **Log out**.

<kbd>![log-out](images/log-out.png ':size=100%')</kbd>

If you are inactive for five minutes on the portal, the system prompts you with the following message. Click **Yes, Keep me signed in** to continue your session.

<kbd>![idle-time-prompt-after-5-mins](images/idle-time-prompt-after-5-mins.png ':size=100%')</kbd>

If you are inactive for 10 minutes on the portal, the system prompts you with the following message.

<kbd>![session-timed-out](images/session-timed-out.png ':size=100%')</kbd>

## [Switch account](#switch-account)
If you are a SA or PA for more than one subscription account in SHIP-HATS, you may need to switch between these accounts to Manage users, Manage Projects, Viewing Plan Details and Viewing Billing Info.

*To switch account:*

1. From the [**Overview**](#viewing-dashboard) page, hover over **Billing Account** at the upper-right area of the page and choose **Switch account**.

<kbd>![switch-account](images/switch-account.png ':size=100%')</kbd>

2. Choose the required billing account to view its dashboard.

<kbd>![switch-account](images/switch-account-choose-account.png ':size=100%')</kbd>
