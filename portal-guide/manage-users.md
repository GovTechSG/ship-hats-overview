# Manage Users
This section describes the following:

* [Invite users](#invite-users)
* [Create Account](#creation-of-account)
* [Approve new users](#approve-new-users)
* [View users](#view-users)
* [Remove users](#remove-users) <!--* [Manage Access](#manage-access)-->
* [Change SA](#change-sa)
* [Change PA](#change-pa)
* [Reactivate users](#reactivate-users)



## [Invite users](#invite-users)
Subscription Admin (SA) and Project Admin (PA) can invite and add users to the subscription. Note that only SA can add a user as PA to their SHIP-HATS projects.

*To invite users:*

1. Log in to <a href="https://www.ship.gov.sg/"> SHIP-HATS portal </a> and ensure you are in the required account. If needed, refer to [Switching account](https://docs.developer.gov.sg/docs/ship-hats-documentation/#/portal-guide/logging-in-and-logging-out?id=switch-account).

2. From the side menu, click **Users > Invite Users**. An invitation link is automatically generated.  
By default, a new invitation link has a 14 days expiry date.  Whenever you invite new users, the same link will be displayed with the remaining expiry date until it expires. In the example below, SA invites a new user to SHIP-HATS. As the invite was created 2 days earlier, the link is valid for the next 12 days.

<kbd>![Invite_users_3](images/Invite_users_3.png ':size=100%')</kbd>

3. Click **Email me** to send this link with the expiry date to your SHIP-HATS registered email address and forward it to the intended users so that they can provide required information in the **Invitation Form**.
Alternatively, click the copy icon to copy and share the invite link with intended users. Note, in this case, make sure to inform the users about the expiry date of this link.

## [Create Account](#creation-of-account)
Users will receive a link to onboard to SHIP-HATS portal upon successful approval. 
Access the link via the onboarding email and perform the following steps: 

1. Select your role. 

<kbd>![create_account](images/invitation-form.png ':size=100%')</kbd>

2. For **public officers**, you will need to enter your **official email address** and click **submit**.

<kbd>![create_account](images/signing2.png ':size=100%')</kbd>

3. For **vendors**, you will be required to enter the following details and click **submit**.

<kbd>![create_account](images/vendor3.png ':size=100%')</kbd>

## [Approve new users](#approve-new-users)
Once a user submits the completed SHIP-HATS **Invitation Form**, Subscription Admin (SA) and Project Admin (PA) will be notified by an email to approve the user registration.

*To approve new user registration:*
1. Log in to <a href="https://www.ship.gov.sg/"> SHIP-HATS portal</a> and ensure you are in the required account. If needed, refer to [Switching account](https://docs.developer.gov.sg/docs/ship-hats-documentation/#/portal-guide/logging-in-and-logging-out?id=switch-account).

<kbd>![pending user approval notification](images/pending_user_approval_notification.png ':size=100%')</kbd>

&nbsp;&nbsp;&nbsp;If there is a pending user approval task for you, it will be displayed in the **ALERTS** section.  

2. Click **View** corresponding to that alert. You will be directed to the **Pending Approval** section.

Alternatively, from the side menu, click **Users** > **All Users**. If there is a pending user approval task, the **Pending** section will display the number of users pending approval. Here, you can view the users that are pending your approval along with their email address.  

Note: If there is a number displayed beside **All Users** menu and **Pending Approval** section, it indicates that many user approvals are pending.  

<kbd>![add user](images/tp-add-user.png ':size=100%')</kbd>

3. Click **Approve** corresponding to the user.

<kbd>![after adding user](images/tp-add-user-3.png ':size=100%')</kbd>

4. You can choose which tools to give access to. When prompted to confirm this action, click **Confirm**. This user is now approved as SHIP-HATS user under this account.

Note: Irrespective of agencies, individuals approved as SHIP-HATS users can be added to any SHIP-HATS project and will be billed under the account that initially approved them.  

## [View users](#view-users)

Subscription Admin (SA) and Project Admin (PA) can view all users associated with a subscription account and their roles in your account.

*To view users:*

1. Log in to <a href="https://www.ship.gov.sg/"> SHIP-HATS portal</a> and ensure you are in the required account. If needed, refer to [Switching account](https://docs.developer.gov.sg/docs/ship-hats-documentation/#/portal-guide/logging-in-and-logging-out?id=switch-account).

2. From the side menu, click **Users > All Users**.

<kbd>![all-users-new](images/all-users-new.png ':size=100%')</kbd>

* If a user is a Subscription Admin, it is indicated by the label **Subscr Admin** beside the username.
* If a user has a Project Admin role in one the projects in the subscription account, it will be indicated in the **Project Role** column.
* You can sort this list in ascending or descending order by anyone of the following:
  * Name
  * Project Role
  * Quota Consumed
  * Last Login
* You can quickly search for a user by typing the username in the search box.

<kbd>![search_user](images/export-csv.png ':size=100%')</kbd>

* Click **Export CSV** to download the user list as a .csv file to your local machine. This csv lists the active and removed users along with the approval and removal details.

<!--## [Manage Access](#manage-access)

*To manage access for a user:*

1. Log in to <a href="https://www.ship.gov.sg/"> SHIP-HATS portal</a> and ensure you are in the required account. If needed, refer to [Switching account](https://docs.developer.gov.sg/docs/ship-hats-documentation/#/portal-guide/logging-in-and-logging-out?id=switch-account).

2. From the side menu, click **Users > All Users**.

<kbd>![all-users-new](images/all-users-new.png ':size=100%')</kbd>

3. Search for the user whose access you want to manage. 
4. From the **Action** column, click ![3_dot](images/3_dot.png) corresponding to the user.  
5. Select **Manage Access**, and select the tools that you want to enable for the user. Following options are available: 
- CI tools
- SonaType tools  

<kbd>![manage-access](images/manage-access.png ':size=100%')</kbd>

6. Click **Proceed**. 
<br />A confirmation message appears, indicating that the user will receive an email regarding the change. 
<br />**Tip:** The Proceed button is enabled only when there is a change to the existing selection.   -->



## [Remove users](#remove-users)

We recommend Subscription Admin (SA) and Project Admin (PA) to periodically review the named users in their account, consumed user quota and remove users who are no longer required.

**Note:** SA and PA can remove a user who does not have the Project Admin or Subscription Admin roles in the subscription account.

*To remove a user:*

1. Log in to <a href="https://www.ship.gov.sg/"> SHIP-HATS portal</a> and ensure you are in the required account. If needed, refer to [Switch account](https://docs.developer.gov.sg/docs/ship-hats-documentation/#/portal-guide/account-management/account-management?id=switch-account).
2. From the side menu, click **Users > All Users**.
3. Search for the user to be removed and from the **Action** column, click ![3_dot](images/3_dot.png) corresponding to the user.
Tip: Refer to [View users](#view-users) to know how to search for users and to sort by **Quota Consumed**.

<kbd>![remove_user](images/remove-users-2.png ':size=100%')</kbd>

4. Choose **Remove User**.

## [Change SA](#change-sa)

To change or transfer the existing SA role to another user, one of the SAs can raise a <a href="https://jira.ship.gov.sg/servicedesk/customer/portal/11/create/364"> service request </a> with the required details, such as the name and email address of the user to whom the SA role is to be transferred.

## [Change PA](#change-pa)
To change or transfer the existing PA role to another user, one of the SAs can add or remove PA on the [SHIP-HATS Portal](http://www.ship.gov.sg)

### To view existing PAs:
1. Log in to [SHIP-HATS Portal](http://www.ship.gov.sg)
2. Click **Users > All users**
3. Click **Project Role**

<kbd>![view user role](images/pa2.png ':size=100%')</kbd>

4. Name of users will be displayed based on the project role.

### To add PAs:
1. Log in to [SHIP-HATS Portal](http://www.ship.gov.sg)
2. Click **Overview** > **Project**.  
<kbd>![overview page](images/overviewpage1.png ':size=100%')</kbd>
3. Click the **pencil** icon.

<kbd>![pa](images/pa1.png ':size=60%')</kbd>

4. Click **+ Add another**. The number of PAs each project is entitled to is based on the [subscription tier](http://www.developer.tech.gov.sg/singapore-government-tech-stack/toolchain/subscription) quota the agency has subscribed to. 

<kbd>![add pa](images/addpacopy.png ':size=60%')</kbd>

5. Choose the designated PA from the drop-down selection and click **Add**. 

<kbd>![add pa](images/add-ppl.png ':size=60%')</kbd>

You have successfully added a PA.

### To remove PAs:
1. Log in to [SHIP-HATS Portal](http://www.ship.gov.sg)
2. Click **Overview** > **Project**.
<kbd>![overview page](images/overviewpage1.png ':size=100%')</kbd>
3. Click the **pencil** icon.

<kbd>![pa](images/pa1.png ':size=60%')</kbd>

4. Hover over to the name you would like to remove 
5. Click **Remove**

<kbd>![remove](images/remove-users.png ':size=60%')</kbd>

6. When prompted, click **Yes**

<kbd>![remove confirmation](images/usure.png ':size=60%')</kbd>

You have successfully removed the user as a PA.

## [Reactivate users](#reactivate-users)

If SHIP-HATS users are inactive for 60 consecutive days, their status changes from **normal user** to **sleeping user**. If the user continues to be inactive, from day 81 onwards an email notification is sent every day to the user until user becomes active (**normal user**) or until it reaches day 90.  

On day 91, if the user is still inactive on SHIP-HATS, user status changes from **sleeping user** to **suspended user**, indicated by a grey avatar.  

<kbd>![profile-legends](images/profile-legends.png ':size=100%')</kbd>

SA and PA can reactivate a suspended user back to their account if required.

*To reactivate a user:*

If you are a TechPass user, the SA can raise a service request using the [TechPass Support form](https://form.gov.sg/#!/5f69797d0666cb0011cc59da). This service request will take 1-3 business days.

If you are not a TechPass user, the SA or PA can follow these steps to reactivate a user:

1. Log in to <a href="https://www.ship.gov.sg/"> SHIP-HATS portal</a> and ensure you are in the required account. If needed, refer to [Switching account](https://docs.developer.gov.sg/docs/ship-hats-documentation/#/portal-guide/logging-in-and-logging-out?id=switch-account).  
2.  From the side menu, click **Users > All Users**.  
3. Search for the user to be reactivated and from the **Action** column, click ![3_dot](images/3_dot.png) corresponding to the user.  

<kbd>![user_status_2](images/user_status_2.png ':size=100%')</kbd>

<br />**Tip:** Refer to [Viewing users](#view-users) to know how to search for users  

4. Choose **Reactivate User**. User, SAs and the requestor will be notified through an email about the reactivation.  

**Notes:**
* Though the reactivated user can log in using the existing credentials, we recommend reactivated users to reset their password. The email sent to the reactivated users includes the link to reset their password.  
* After a user has been reactivated, an email notification about this reactivation is sent to the requestor and the SAs.
