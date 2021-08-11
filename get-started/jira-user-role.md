# Atlassian Jira - Roles and Permissions
You can use Jira for bug tracking, issue tracking and project management. <a href="https://docs.developer.gov.sg/docs/ship-hats/#/user-roles-permisions">SHIP-HATS Project Admin (PA)</a> can add Atlassian Jira to the SHIP-HATS project.

Now that you have added Jira as your project tool, let us look at the project roles recommended for all users.

### Jira project roles

There are three types of user roles for a SHIP-HATS Jira project. All these roles and permissions assigned are at Jira project level. Users can be assigned to more than one project role.

- Administrator: By default, SHIP-HATS’ Project Admin is assigned with this role in the Jira project. Administrator can manage the project such as assign or revoke user roles and create components and manage default assignees for issues.
- Users: Administrator adds required users to the Jira project. Users can log issues for the Jira project.
- Developer: Administrator adds required developers to the Jira project. Person with Developer role can work on issues in the Jira project.

### SHIP-HATS - Jira role mapping
 
| SHIP-HATS Users | Jira Users |
| :-------- | ------------- |
| Project Admin |Administrator at project level. This role is assigned by default when Jira is added to the SHIP-HATS project. Administrator can assign project roles to other users and there can be more than one Administrator. |
| User | SHIP-HATS users can be assigned as Administrator, Users and Developer in the Jira project. |


### Permissions for subscription tiers
Jira is available in all subscription tiers.

### Permissions for built-in roles
The permissions applicable to project roles depend on the permission scheme assigned for your project.


*To view permissions applicable for all user roles:*
1. In <a href="https://gccprod-my.sharepoint.com/personal/ramakrishnan_sowmya_tech_gov_sg/Documents/SHIP-HATS/Documentation%20&%20Training/jira.ship.gov.sg">SHIP Jira</a>, go to Projects to choose your project.
2. Click **Project settings** at the lower-left.
3. From the sidebar, select **Permissions**. You will be able to view the **Project Permissions**.

The below table is an example of the <a href="roles"> Jira project roles</a> and applicable permissions.


**Projects**

|  | Administrator | Users | Developer |
| :------ | -------- | ----------| ----- |
| Administer Projects | ✓ |   |   |
| Browse projects | ✓ | ✓ | ✓ |
| Manage Sprint | ✓ |   |   |
| Start/Complete Sprint | ✓ |   |   |
| View Development Tools | ✓ |   | ✓ |
| View Read-only Workflow | ✓ | ✓ | ✓ |

**Issues** 

|  | Administrator | Users | Developer |
| :------ | -------- | ----------| ----- |
| Archive Issues | ✓ |   |   |
| Assignable User | ✓ |   | ✓ | 
| Assign Issues | ✓ |   | ✓ | 
| Close Issues | ✓ |   | ✓ |
| Create Issues | ✓ | ✓ | ✓ |
| Delete Issues | ✓ |   | ✓ |
| Edit Issues | ✓ |   | ✓ |
| Link Issues | ✓ | ✓ | ✓ |
| Modify Reporter | ✓ |   |   |
| Move Issues | ✓ |   | ✓ |
| Resolve Issues | ✓ |   | ✓ |
| Schedule Issues | ✓ |   | ✓ |
| Set Issue Security | ✓ | ✓ | ✓ |
| Transition Issues | ✓ | ✓ | ✓ |

**Voters and Watchers**

|  | Administrator | Users | Developer |
| :------ | -------- | ----------| ----- |
| Manage Watchers | ✓ |   | ✓ |
| View Voters and Watchers | ✓ |   | ✓ |

**Comments** 

|  | Administrator | Users | Developer |
| :------ | -------- | ----------| ----- |
| Add Comments | ✓ | ✓ | ✓ |
| Delete All Comments | ✓ |   |   |
| Delete Own Comments | ✓ | ✓ | ✓ |
| Edit All Comments | ✓ |   | ✓ |
| Edit Own Comments | ✓ | ✓ | ✓ |

**File Attachments** 

|  | Administrator | Users | Developer |
| :------ | -------- | ----------| ----- |
| Create Attachments | ✓ | ✓ | ✓ |
| Delete All Attachments | ✓ |   |   |
| Delete Own Attachments | ✓ | ✓ | ✓ |

**Time Tracking** 

|  | Administrator | Users | Developer |
| :------ | -------- | ----------| ----- |
| Delete All Worklogs | ✓ |   |   |
| Delete Own Worklogs | ✓ | ✓ | ✓ |
| Edit All Worklogs | ✓ |   | ✓ |
| Edit Own Worklogs | ✓ | ✓ | ✓ |
| Work On Issues | ✓ |   | ✓ |

#### Jira user groups
Groups are an easier and efficient way to manage user access for multiple users. Users can raise a <a href="https://jira.ship.gov.sg/servicedesk/customer/portal/11/">service request</a> with the required group name and user details such as name and email address. Crowd administrator from the SHIP-HATS team then evaluates the request and approves it accordingly.


If approved, the group is created with the agency name prefixed to it. For example, *govtech-codex-documentation*. If a group is already created for managing users in any one of the Atlassian products added to your project on SHIP-HATS, you will be able to see that in all the integrated Atlassian products. Note that user groups are created at a global level and are visible to all SHIP-HATS users. Jira project administrators can manage user groups for the project.

#### Jira custom permissions
Administrator can raise a <a href="https://jira.ship.gov.sg/servicedesk/customer/portal/11/">service request</a> to change project permissions for an existing user role.

#### Jira custom-roles
Although we highly encourage you to use Jira project roles, if it is critical for your project to have custom project roles, the Administrator can raise a <a href="https://jira.ship.gov.sg/servicedesk/customer/portal/11/">service request</a> to the Jira administrator in the SHIP-HATS team.


Jira administrator from the SHIP-HATS team evaluates the requests on a case-by-case basis. Note that such custom project roles are created at a global level and they are visible to all SHIP-HATS users.


#### Additional Resources
Refer to <a href="https://confluence.atlassian.com/adminjiraserver0816/managing-project-permissions-1063164378.html"> Jira Documentation</a> for more information on managing project permissions in Jira.
