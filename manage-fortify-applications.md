# Manage Fortify applications

**Why Fortify?**

Fortify Static Code Analyzer (SCA) is used to analyse the security vulnerabilities in your applications. Project Admins can add applications to their projects in the [SHIP-HATS portal](https://www.ship.gov.sg/) for Static Code Analysis(SCA) using Fortify SCA and Dynamic Code Analysis(DCA) using Fortify WebInspect. Both SCA and DCA scan results can be sent to the same Fortify Application.

?> Note: App, application and Fortify application are the same and are used interchangeably in this document.

**Audience**

- [SHIP-HATS Project Admin (PA)](https://docs.developer.gov.sg/docs/ship-hats/#/user-roles-permissions)

**Objective**

This document guides PAs to do the following from [SHIP-HATS portal](https://www.ship.gov.sg/):

- [Add applications to Fortify Software Security Center (SSC)](#add-applications-to-fortify-ssc)
- [Add users to Fortify applications](#add-users-to-fortify-applications)
- [Manage user role in Fortify applications](#manage-user-role-in-fortify-applications)
- [Remove users from Fortify applications](#remove-users-from-fortify-applications)
- [Get token for Fortify applications](#get-token-for-fortify-application)
- [Remove applications from Fortify SSC](#remove-applications-from-fortify-ssc)

## [Add applications to Fortify SSC](#add-applications-to-fortify-ssc)

1. From the side menu, click  **Projects**  >  **All Projects** to view all the projects in this subscription account. If needed, refer to [**Switch account**](https://docs.developer.tech.gov.sg/docs/ship-hats-documentation/#/manage-account?id=switch-account).

2. Find the project and click  **Manage**.

3. Click **QA &amp; Security**.

    <kbd>![add-qa-sec-tool](add-qa-sec-tool.png ':size=75%')</kbd>

4. Click **Add tool**.

    <kbd>![add-fortify-tool](add-fortify-tool.png ':size=75%')</kbd>

5. Click the drop-down menu and choose **Fortify SCA &amp; WebInspect**.

    <kbd>![add-app-name-quota](add-app-name-quota.png ':size=75%')</kbd>

    System displays the current quota available to add applications. In the above example, one application can be added as per the quota displayed.

6. Specify **App name** and click **Add**. The application gets added to the project. *GOVTECH-Documentation-Marvel Heroes* is an eaxmple application.

    <kbd>![added-app](added-app.png ':size=75%')</kbd>

?> Note: PA can [Remove applications from Fortify SSC](#remove-applications-from-fortify-ssc).

## [Add users to Fortify applications](#add-users-to-fortify-applications)

PAs can add users to the added Fortify applications and manage their roles and permissions on Fortify User Management portal.

1. Log in to [Fortify User Management portal](https://ssc-roles.hats.stack.gov.sg/).
2. Enter your SHIP-HATS **Username**, **Password** and click **Log in**.
3. Click the drop-down menu and choose the required app.

    <kbd>![select-app-to-add-users](select-app-to-add-users.png ':size=75%')</kbd>

    By default, PAs of associated project in SHIP-HATS dynamically are added to the application as users.

4. Click **Add User** to specify the required details.

    <kbd>![add-users](add-users.png ':size=75%')</kbd>

5. Click the **User(s)** to select the required users.

    <kbd>![add-multiple-users-apps](add-multiple-users-apps.png ':size=75%')</kbd>

6. To add the selected **User(s)** for other applications within this subscription, click **App(s)** and select the required applications.

7. Click **Add**. 

<!--You will see a success message as shown below. <kbd>![](93cdf038eb786794.png ':size=75%')</kbd>-->

?> Note: By default, all the application users have Viewer permission.

## [Manage user role in Fortify applications](#manage-user-role-in-fortify-applications)

PA can assign [**Security Lead** , **Security Tester** or **Report Uploader**](https://docs.developer.tech.gov.sg/docs/ship-hats-documentation/#/fortify-user-roles-and-permissions) role to all application users excluding other PAs.

?> Note: Role assigned to a user in Fortify is global and hence a user will have the same role across all the apps.

1. Log in to [Fortify User Management portal](https://ssc-roles.hats.stack.gov.sg/).
2. Enter your SHIP-HATS **Username**, **Password** and click **Log in**.
3. Click the **APP** drop-down menu to choose the app.

    <kbd>![select-app-to-add-users](select-app-to-add-users.png ':size=75%')</kbd>

    You will see the list of current users for this application.

4. Hover over the existing **Role** of the user to view the list of available roles.

    <kbd>![choose-roles-for-users](choose-roles-for-users.png ':size=75%')</kbd>

    >**Note:** You cannot modify the roles of other PAs.

5. Assign the required **Role**. 

<!-- You will see a success message as shown below.

<kbd>![](8596594456fb6478.png ':size=75%')</kbd> -->

## [Remove users from Fortify applications](#remove-users-from-fortify-applications)

PAs can remove all users excluding fellow PAs of the project in which the application was added. To remove fellow PAs, remove them from SHIP-HATS project level.

**To remove users from Fortify applications:**

1. Log in to [Fortify User Management portal](https://ssc-roles.hats.stack.gov.sg/).
2. Enter your SHIP-HATS **Username, Password** and click **Log in**.
3. Click the **APP** drop-down menu to choose the app.

    <kbd>![select-app-to-add-users](select-app-to-add-users.png ':size=75%')</kbd>

    You will see the list of current users for this application.

    <kbd>![remove-users-legends-a](remove-users-legends-a.png ':size=75%')</kbd>

4. Click **Remove** corresponding to the user.

## [Get token for Fortify application](#get-token-for-fortify-application)

Project users need a token to authenticate themselves on Fortify before uploading scan results to [Fortify Software Security Center (SSC)](https://ssc.hats.stack.gov.sg/ssc/#!/). When PAs add Fortify applications to a project using SHIP-HATS portal, a token is available, and this has to be shared with the required users.

Tokens are at project level and is generated when the first Fortify application is added to the project. Hence, same token is valid for all the Fortify applications added to this project and is valid for a year from the date of its generation.

### To get token ID for Fortify applications:

1. From the side menu, click  **Projects**  >  **All Projects**  to view all the projects in this subscription account. If needed, refer to [**Switch account**](https://docs.developer.tech.gov.sg/docs/ship-hats-documentation/#/manage-account?id=switch-account).
2. Find the project and click  **Manage**.
3. Click **QA &amp; Security**.

    <kbd>![share-token-id-manage](share-token-id-manage.png ':size=75%')</kbd>

4. Click **Manage**. The **Manage Tool** pane is displayed.

    <kbd>![share-token-id-manage](share-token-id-manage.png ':size=75%')</kbd>

5. Click the drop-down arrow and choose **Token for bamboo pipeline**.

    <kbd>![token-id-menu](token-id-menu.png ':size=75%')</kbd>

6. Copy the **Decoded Token ID** and share this to the required users.

    <kbd>![copy-token-id](copy-token-id.png ':size=75%')</kbd>

Tip: While PAs share tokens with users, make sure to include the project names to map them with the shared tokens.

## [Remove applications from Fortify SSC](#remove-applications-from-fortify-ssc)

PA [adds applications](https://docs.developer.tech.gov.sg/docs/ship-hats-documentation/#/manage-fortify-applications?id=add-applications-to-fortify-ssc) and removes applications in Fortify using the [SHIP-HATS portal](https://www.ship.gov.sg/). When an application is removed, all its users are automatically  removed.

### To remove applications from Fortify:

1. From the side menu, click  **Projects**  >  **All Projects**  to view all the projects in this subscription account. If needed, refer to [**Switch account**](https://docs.developer.tech.gov.sg/docs/ship-hats-documentation/#/manage-account?id=switch-account).
2. Find the project and click  **Manage**.
3. Click **QA &amp; Security**.

![latest-delete-app](latest-delete-app.png ':size=75%')</kbd>

4. Click **Manage**. The **Manage Tool** pane is displayed.

    <kbd>![remove-app-choose-option](remove-app-choose-option.png ':size=75%')</kbd>

5. Click the drop-down arrow and choose **Remove app**.

    <kbd>![remove-app-option](remove-app-option.png ':size=75%')</kbd>

    All the applications added for this project will be listed.

    <kbd>![latest-choose-app-to-be-deleted](latest-choose-app-to-be-deleted.png ':size=75%')</kbd>

6. Click **Remove** beside the application.

    <kbd>![latest-remove-app-confirmation](latest-remove-app-confirmation.png ':size=75%')</kbd>

7. Type the application name without double quotes and click **Proceed**.

?> Note: Text you enter to confirm is case-sensitive.
