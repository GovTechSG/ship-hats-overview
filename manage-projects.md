# Manage Projects

This section explains how a Subscription Admin creates SHIP-HATS projects and how Project Admin manages these projects by adding the required users and tools.

- [Create new projects](#create-new-projects)
- [Add project admins](#add-project-admins)
- [View projects](#view-projects)
- [Add project tools](#add-project-tools)
- [Create Project tool with customised project key](#creation-of-project-tool-with-customised-project-key)
- [Manage user groups within a Project tool](#manage-user-groups-within-a-project-tool)
- [Manage users within a Project Tool](#manage-users-within-a-project-tool)
- [Remove projects](#remove-projects)
- [Remove project tools](#remove-project-tools)

## Create new projects

Subscription Admin (SA) can create new projects in SHIP-HATS and manage them. SAs assign Project Admins (PA). Both SA and PA can manage the projects by adding project tools and add users.

### To create a new project

1. From the side menu, click **Projects** > **Create New**.  

>**Tip:** Alternatively, if you are viewing **All Projects**, click **Create Project**.  

<kbd>![create-new-project](create-new-project-2.png ':size=100%')</kbd>

2. Provide information in the following fields:

    |Field|Description|
    |---|---|
    | **Project Name** |Specify name of the project. 
    |**Project Description**| Specify details of the project. 
    |**Project Admin 1**| Select Project Admin from the drop-down list. If *First Name* and *Last Name* were not provided when creating a new user account, email address will appear in the drop-down list.
    |**Project Admin 2**| This is an optional field. Select a second Project Admin from the drop-down list. If *First Name* and *Last Name* were not provided when creating a new user account, email address will appear in the drop-down list. 
3. Click **Create Project**. The created project details are displayed as shown below.

    <kbd>![newly-created-project](newly-created-project.png ':size=100%')</kbd>

SA or PA can add tools and additional PAs. 
> **Note:** The number of PAs each project is entitled to is based on the [subscription tier](https://www.developer.tech.gov.sg/products/categories/devops/ship-hats/subscription) quota for which the agency has subscribed.

## Add project admins

Subscription Admins can add Project Admins using the SHIP-HATS portal. When creating a project in an account, it is mandatory to specify at least one Project Admin. SAs can add any additional PAs anytime in the future.  

> **Note:** The number of PAs each project is entitled to is based on the [subscription tier](https://www.developer.tech.gov.sg/products/categories/devops/ship-hats/subscription) quota for which the agency has subscribed.

### To add a project admin

1. From the side menu, click **Projects** > **All Projects** to view all the projects in this subscription account. If needed, refer to [Switching account](https://docs.developer.gov.sg/docs/ship-hats-documentation/#/manage-account?id=switch-account).
2. Locate the project, and then click **Manage**.

    <kbd>![add-pa-1-resized](add-pa-1-resized.png ':size=100%')</kbd>

3. Click the edit icon.  
    The **Manage Admin** panel appears.

    <kbd>![add-pa-2-resized](add-pa-2-resized.png ':size=100%')</kbd>

4. Click **Add another** to select the required user from the drop-down list.

    <kbd>![add-pa-3-correct](add-pa-3-correct-resized.png ':size=100%')</kbd>

    >**Note:** If *First Name* and *Last Name* were not provided when creating a new user account, email address will appear in the drop-down list.
5. Click **Add** to add this user as a project admin. Once successfully added, an email notification will be sent to the requesting SA with copy sent to the other SA and the newly added PA.

>**Note:** To know how to remove a Project Admin, refer to **Remove User**.

## View projects

SA and PAs of a subscription account can view all the projects of the subscription account.

### To view a project in a subscription account

1. From the side menu, click **Projects** > **All Projects**.

    Tile view of all the projects in this subscription account is displayed. If needed, refer to [Switching account](https://docs.developer.gov.sg/docs/ship-hats-documentation/#/manage-account?id=switch-account).

    <kbd>![](view-all-projects-tile-view.png ':size=100%')</kbd>

2. Click **Manage** to view tools that are currently added to the project.

## Add project tools

SA or PA can add the required project tools as explained below. You can add tools for **Development**, **Build**, **QA &amp; Security**, and **Release** phases as per the tools quota allotted for your subscription type. 

>**Notes:** 
>- If you want to add *Nexus Repo* or *Release and Deploy* tools, you must raise a [service request](https://jira.ship.gov.sg/servicedesk/customer/portal/11/).
>- If you want to add SonarQube and add related applications, you must have logged in to SonarQube at least once.


### To add project tools

1. From the side menu, click **Projects** > **All Projects** to view all the projects in this subscription account. If needed, refer to [Switching account](https://docs.developer.gov.sg/docs/ship-hats-documentation/#/manage-account?id=switch-account).
2. Locate the project to which you want to add a tool, and then click **Manage**.

3. Go to the required tab, and then click **Add tool**.  


    For example if you want to add Jira, go to **Development** tab, and then click **Add tool**.

    <kbd>![add-new-development-tool](add-new-development-tool.png ':size=100%')</kbd>

5. Select the required tool, and then click **Add**. The selected tool gets integrated with your SHIP-HATS project and a project is automatically created in the tool with the same name. For example, if the SHIP-HATS project name is *Govtech-Documentation*, the newly added JIRA project inherits this name.

    <kbd>![project-created-for-tools](project-created-for-tools.png ':size=100%')</kbd>

- **Development:** You can add following tools using this tab:
    - **Jira**
    - **Confluence**
    - **Bitbucket** 
- **Build:** You can add following tools using this tab:
    - **Bamboo**
    - **Nexus IQ:** Provide values in the **Application Name** and **Application ID** fields to enable the **Add** button.
    - **Nexus Repo:** Submit a ticket to add this tool.
- **QA &amp; Security:** You can add following tools using this tab:
    - **pCloudy Device Farm & HATS Browser Farm** 
    - **SonarQube - Community Edition:** Provide value in the **App name** field to enable the **Add** button.
    - **SonarQube - Developer Edition:** Provide value in the **App name** field to enable the **Add** button.
    - **Fortify SCA & WebInspect:** Provide value in the **App name** field to enable the **Add** button. When you are this tool, the remaining quota will appear for your subscription. 
    - **Container Image Scanner:** Provide values in the **Scanner type** and **App name** fields to enable the **Add** button.


>**Notes:**
>- When adding tools such as WebInspect Fortify SCA under the **QA &amp; Security** tab, the system displays the quota remaining for your subscription as shown below.
><kbd>![tool-quota](tool-quota-resized-2.png ':size=100%')</kbd>
>- After you have reached the quota, the respective tool name(s) will be disabled in the **Select Tool** drop-down list. If you still want to add these tools, raise a [service request](https://jira.ship.gov.sg/servicedesk/customer/portal/11/).


## Creation of Project tool with customised project key
Subscription Admin (SA) and Project Admin (PA) can customise the project keys when adding app tools on SHIP-HATS. This is currently applicable for Jira, Bitbucket, and Confluence.  

### To customise project key

1. Go to **Projects> All Projects>** > Manage > to view and select the relevant project. 
2. Click Add tool under **Development** tab.
3. Choose the required tool.

    ![chara](chara.png)

4.  Select **Customise Project Key**.

    ![customise](customise.png)

5. Enter the required project key. It can only have 2-10 characters, consisting of uppercase letters A-Z and numbers from0-9. First character must be an alphabet. 

    ![add](addnewkey.png)

<!--CODEX-49288 https://gdsjira.ship.gov.sg/browse/PORTAL-2133 -->


## Manage user groups within a project tool

As a Subscription Admin or a Project Admin, you can manage user groups within a project tool or app. You can manage user groups for the following tools:
- Bamboo
- Bitbucket
- Confluence
- JIRA
- Nexus IQ

### To manage user groups for your project tool or app

1. Go to **Projects** > **All Projects**.

    <kbd>![All Projects](portal-projects-all-projects.png)</kbd>

1. Navigate to your project, and then click **Manage** on the project tool whose users you want to manage. 

    <kbd>![All Projects](portal-projects-manage-app.png)</kbd>

1. In the **Manage Tool** window that appears, from the dropdown, select **Manage/add user group**. 

    <kbd>![All Projects](portal-projects-manage-tool.png  ':size=60%')</kbd>

1. To manage users, follow the on-screen instructions. 




## Manage Users within a Project Tool

As a Subscription Admin or a Project Admin, you can manage users within a project tool or app. You can manage users for the following tools:
- Bamboo
- Bitbucket
- Confluence
- JIRA
- Nexus IQ

### To manage users for your project tool or app

1. Go to **Projects** > **All Projects**.

    <kbd>![All Projects](portal-projects-all-projects.png)</kbd>

1. Navigate to your project, and then select **Manage**.

    <kbd>![All Projects](portal-projects-manage.png  ':size=60%')</kbd>

1. Click **Manage** on the project tool whose users you want to manage. 

    <kbd>![All Projects](portal-projects-manage-app.png)</kbd>

1. In the **Manage Tool** window that appears, from the dropdown, select **Manage/add user**. 

    <kbd>![All Projects](portal-projects-manage-tool.png  ':size=60%')</kbd>

1. To manage users, follow the on-screen instructions. 

    >**Note:** The link to tool or app server, includes the project key that you selected. This enables you to get to the project in the tool or app server directly. This is applicable for all Atlassian apps (Bamboo, Bitbucket, Confluence, and JIRA).  
    >
    ><kbd>![All Projects](portal-projects-manage-users.png  ':size=60%')</kbd>

## Remove projects

As a Subscription Admin, you can remove a project as long as no tool has been added to it.

### To remove a project

1. From the side menu, click **Projects** > **All Projects** to view all the projects in this subscription account. If needed, refer to [Switching account](https://docs.developer.gov.sg/docs/ship-hats-documentation/#/manage-account?id=switch-account).
1. Locate the project, and then click **Manage**. You will see ![remove-project-icon](remove-project-icon.png) beside the project name as shown below.

    <kbd>![remove-project](remove-project.png ':size=100%')</kbd>
1. Click the three dots, and then choose **Remove project**.

## Remove project tools
As a Subscription Admin or a Project Admin, you can remove a tool or an app when it is not required. You can remove the following tools: 
- Confluence
- Bitbucket
- Jira
- Nexus IQ
- WebInspect

### To remove a project tool
1. Go to **Projects** > **All Projects**.
1. Navigate to the project whose tool you want to remove, and then click **Manage**.
1. On the tool that want to remove, click **Manage**.  
    The **Manage Tool** window appears.
1. From the dropdown, select **Remove App**. 
    **Select App to Remove:** appears, displaying a list of apps. 

    ![removetool](removetool.png)

1. Next to the app that want to remove, click **Remove**.  
    The **Remove** window appears.

    ![remove](confirmremove.png)
1. Enter the requested information, and then click **Proceed**.  

    ![proceed](proceed.png)
    The selected app is removed. If this the last app for the tool, the project tool is also removed. 