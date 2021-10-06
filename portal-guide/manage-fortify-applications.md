# Manage Fortify applications

**Why Fortify?**

Fortify Static Code Analyzer (SCA) is used to analyse the security vulnerabilities in your applications. Project Admins can add applications to their projects in the [SHIP-HATS portal](https://www.ship.gov.sg/) for Static Code Analysis(SCA) using Fortify SCA and Dynamic Code Analysis(DCA) using Fortify WebInspect. Both SCA and DCA scan results can be sent to the same Fortify Application.

?> Note: App, application and Fortify application are the same and are used interchangeably in this document.

**Audience**

- [SHIP-HATS Project Admin (PA)](https://docs.developer.gov.sg/docs/ship-hats/#/user-roles-permisions)

**Objective**

This document guides PAs to do the following from [SHIP-HATS portal](https://www.ship.gov.sg/):

- [Add applications to Fortify Software Security Center (SSC)](#add-applications-to-fortify-ssc)
- [Add users to Fortify applications](#add-users-to-fortify-applications)
- [Manage user role in Fortify applications](#manage-user-role-in-fortify-applications)
- [Remove users from Fortify applications](#remove-users-from-fortify-applications)
- [Get token ID for Fortify applications](#get-token-for-fortify-application)
- [Remove applications from Fortify SSC](#remove-applications-from-fortify-ssc)

## [Add applications to Fortify SSC](#add-applications-to-fortify-ssc)

1. From the side menu, click  **Projects**  >  **All Projects** to view all the projects in this subscription account. If needed, refer to [**Switch account**](https://docs.developer.tech.gov.sg/docs/ship-hats-documentation/#/portal-guide/manage-account?id=switch-account).

2. Find the project and click  **Manage.**

3. Click **QA &amp; Security**.

<kbd>![add-qa-sec-tool](images/add-qa-sec-tool.png ':size=75%')</kbd>

4. Click **Add tool**.

<kbd>![add-fortify-tool](images/add-fortify-tool.png ':size=75%')</kbd>

5. Click the drop-down menu and choose **Fortify SCA &amp; WebInspect**.

<kbd>![add-app-name-quota](images/add-app-name-quota.png ':size=75%')</kbd>

System displays the current quota available to add applications. In the above example, one application can be added as per the quota displayed.

6. Specify **App name** and click **Add**. The application gets added to the project. *GOVTECH-Documentation-Marvel Heroes* is an eaxmple application.

<kbd>![added-app](images/added-app.png ':size=75%')</kbd>

?> Note: PA can [Remove applications from Fortify SSC](#remove-applications-from-fortify-ssc).

## [Add users to Fortify applications](#add-users-to-fortify-applications)

PAs can add users to the added Fortify applications and manage their roles and permissions on [Fortify User](https://ssc-roles.hats.stack.gov.sg/)Management portal.

1. Log in to [Fortify User Management](https://ssc-roles.hats.stack.gov.sg/) portal.
2. Enter your SHIP-HA **TS Username, Password** and click **Log in**.
3. Click the drop-down menu and choose the required app.

<kbd>![select-app-to-add-users](images/select-app-to-add-users.png ':size=75%')</kbd>

By default, PAs of associated project in SHIP-HATS dynamically get added to the application as users.

4. Click **Add User** to specify the required details.

<kbd>![add-multiple-users-apps](images/add-multiple-users-apps.png ':size=75%')</kbd>

5. Click the **User(s)** to select the required users.
6. To add the selected **User(s)** for other applications within this subscription, click **App(s)** and select the required applications.
7. Click **Add**. <!--You will see a success message as shown below. <kbd>![](images/93cdf038eb786794.png ':size=75%')</kbd>-->

?> Note: By default, application users have Viewer permission.

## [Manage user role in Fortify applications](#manage-user-role-in-fortify-applications)

PA can assign **Security Lead** , **Security Tester** or **Report Uploader** role to the application users excluding other PAs.

?> Note: Role assigned to a user in Fortify is global and hence a user will have the same roles across all the apps.

1. Log in to [Fortify User Management](https://ssc-roles.hats.stack.gov.sg/) portal.
2. Enter your SHIP-HA **TS Username, Password** and click **Log in**.
3. Click the **APP** drop-down menu to choose the app.

<kbd>![select-app-to-add-users](images/select-app-to-add-users.png ':size=75%')</kbd>

You will see the list of current users for this application.

4. Hover over the existing **Role** of the user to view the list of available roles.

<kbd>![choose-roles-for-users](images/choose-roles-for-users.png ':size=75%')</kbd>

?> Note: You cannot modify the roles of other PAs.

5. Assign the required **Role**. 

<!-- You will see a success message as shown below.

<kbd>![](images/8596594456fb6478.png ':size=75%')</kbd> -->

## [Remove users from Fortify applications](#remove-users-from-fortify-applications)

PAs can:

- Remove themselves from a Fortify application.
- Remove users excluding other PAs of the same project.
- Remove PAs of a different project.

1. Log in to [Fortify User Management](https://ssc-roles.hats.stack.gov.sg/) portal.
2. Enter your SHIP-HATS **Username, Password** and click **Log in**.
3. Click the **APP** drop-down menu to choose the app.

<kbd>![select-app-to-add-users](images/select-app-to-add-users.png ':size=75%')</kbd>

You will see the list of current users for this application.

<kbd>![remove-users-legends](images/remove-users-legends.png ':size=75%')</kbd>

4. Click **Remove** corresponding to the user.

## [Get token for Fortify application](#get-token-for-fortify-application)

Project users need a token to authenticate themselves on Fortify before uploading scan results to Fortify Software Security Center (SSC). When PAs add Fortify applications to a project using SHIP-HATS portal, a token is available, and this is shared with the required users.

Tokens are at project level and is generated when the first Fortify application is added to the project. Hence, same token is valid for all the Fortify applications added to this project and is valid for a year from the date of its generation.

*To get token ID for Fortify applications:*

1. From the side menu, click  **Projects**  >  **All Projects**  to view all the projects in this subscription account. If needed, refer to [**Switch account**](https://docs.developer.tech.gov.sg/docs/ship-hats-documentation/#/portal-guide/manage-account?id=switch-account).
2. Find the project and click  **Manage.**
3. Click **QA &amp; Security**.

<kbd>![share-token-id-manage](images/share-token-id-manage.png ':size=75%')</kbd>

4. Click **Manage**. The **Manage Tool** pane is displayed.

<kbd>![share-token-id-manage](images/share-token-id-manage.png ':size=75%')</kbd>

5. Click the drop-down arrow and choose **Token for bamboo pipeline**.

<kbd>![token-id-menu](images/token-id-menu.png ':size=75%')</kbd>

6. Copy the Decoded Token ID and share this to the required users.

<kbd>![copy-token-id](images/copy-token-id.png ':size=75%')</kbd>

Tip: When PAs share the token IDs with the users, make sure to include the project name to map the token ids.

## [Remove applications from Fortify SSC](#remove-applications-from-fortify-ssc)

PA adds and removes applications in Fortify using the [SHIP-HATS portal](https://www.ship.gov.sg/). When an application is removed, all its users automatically are unassigned.

*To remove applications from Fortify:*

1. From the side menu, click  **Projects**  >  **All Projects**  to view all the projects in this subscription account. If needed, refer to [**Switch account**](https://docs.developer.tech.gov.sg/docs/ship-hats-documentation/#/portal-guide/manage-account?id=switch-account).
2. Find the project and click  **Manage.**
3. Click **QA &amp; Security**.

![latest-delete-app](images/latest-delete-app.png ':size=75%')</kbd>

4. Click **Manage**. The **Manage Tool** pane is displayed.

<kbd>![remove-app-choose-option](images/remove-app-choose-option.png ':size=75%')</kbd>

5. Click the drop-down arrow and choose **Remove app**.

<kbd>![remove-app-option](images/remove-app-option.png ':size=75%')</kbd>

All the applications added for this project will be listed.

<kbd>![latest-choose-app-to-be-deleted](images/latest-choose-app-to-be-deleted.png ':size=75%')</kbd>

6. Click **Remove** beside the application.

<kbd>![latest-remove-app-confirmation](images/latest-remove-app-confirmation.png ':size=75%')</kbd>

7. Type the application name without double quotes and click **Proceed**.

?> Note: Text you enter to confirm is case-sensitive.
