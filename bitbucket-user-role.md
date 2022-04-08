# Atlassian Bitbucket – Roles and Permissions

You can use Bitbucket as a centralised place to manage your project source code repositories for an efficient source code management. <a href="https://docs.developer.gov.sg/docs/ship-hats-documentation/#/user-roles-permissions">SHIP-HATS Project Admin (PA)</a> can add Atlassian Bitbucket to a SHIP-HATS project. 

**Topics**
- [Bitbucket User Roles and Permissions](#bitbucket-user-roles-and-permissions)
- [Assign Permissions](#assign-permissions)
- [Review Permissions](#review-permissions)



## Bitbucket User Roles and Permissions
After you add Bitbucket as your project tool, a Bitbucket project is created. Please refer to <a href="https://confluence.atlassian.com/bitbucketserver0711/using-project-permissions-1047557542.html">Bitbucket Project Permissions</a> to know more about the possible permissions for users added to the project. 

### SHIP-HATS - Bitbucket role mapping
| SHIP-HATS Users | Bitbucket Users |
| :-------- | --------- |
| Project Admin | Administrator for the project. </br> This role is assigned by default when Bitbucket is added to the SHIP-HATS project. Administrator can assign project roles to other users and there can be more than one Administrator. |
| Users | SHIP-HATS users can be assigned as an administrator or added as user to the project. |

### Bitbucket Users
You can add and manage users as individual users and group. Administrator can view project permissions assigned for users and groups.

### To view project permissions:

1. In <a href="https://bitbucket.ship.gov.sg">SHIP Bitbucket</a>, go to Projects and choose your project. 

1. Click ![settings](settings.png) **Project settings**. If you do not have Admin permissions, you will not be able to view this option.

    ![bitbucket](bitbucket.png)


1. From the sidebar, select **Project permissions**. You will be able to view the **Project permissions**.

### Bitbucket User access  

Administrator can add users individually and manage their permissions.

### Bitbucket Group access   

Groups are an easier and efficient way to manage user access for multiple users.  Users can raise a <a href="https://jira.ship.gov.sg/servicedesk/customer/portal/11/">service request</a> with the required group name, project name and user details such as name and email address. Crowd administrator in the SHIP-HATS team evaluates the request and approves it accordingly.  

If approved, the group is created with the agency name prefixed to it. For example, MOE-BCAS. If a group was already created for managing users in any one of the Atlassian products added to your project on SHIP-HATS, you would be able to see that in all the integrated Atlassian products. Bitbucket project administrators can manage user groups for the project.

### Additional Resources
Please refer to <a href="https://confluence.atlassian.com/bitbucketserver0711/using-project-permissions-1047557542.html"> Bitbucket Project Permissions</a> to know more about the possible permissions for the users added to a project.

## Assign Permissions

Assign permissions as per the image below:

![bitbucket permissions](ship-bitbucket-assign-permission.png)

## Review Permissions

As part of [IM8 Security policy](https://intranet.mof.gov.sg/portal/IM/Themes/IT-Management/Security/Topics/Application-Development-Security.aspx) (Clause # 2.3/S1), we recommend agencies onboarded to SHIP services to review the project’s permission, user access, roles and emails regularly for all the applications (Jira, Confluence, Bamboo, Bitbucket). The project admins can do the following:

### To review the user access in project:

1. Navigate to **Bitbucket** > **Project Settings** > **Project Permissions**.

    ![bitbucket project permissions](ship-bitbucket-review-project-permission.png)

### To review the user access for branch:

1. Navigate to **Bitbucket** > **Project Settings** > **Branch Permissions**.

    ![bitbucket branch permissions](ship-bitbucket-review-branch-permission.png)









