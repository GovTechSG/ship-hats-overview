# Manage Users
This section describes the following:

- [Invite users](#invite-users)
- [Create Account](#create-account)
- [Approve new users](#approve-new-users)
- [View users](#view-users)
- [Generate a User Report](#generate-a-user-report)
- [Remove users](#remove-users) 
- [Manage Access](#manage-access)
- [Change SA](#change-sa)
- [Change PA](#change-pa)
- [Reactivate users](#reactivate-users)



## [Invite users](#invite-users)
Subscription Admin (SA) and Project Admin (PA) can invite and add users to the subscription. Note that only SA can add a user as PA to their SHIP-HATS projects.

### To invite users:

1. Log in to the [SHIP-HATS portal](https://www.ship.gov.sg/).  
   Make sure that you are in the required account. If needed, refer to [Switching account](https://docs.developer.gov.sg/docs/ship-hats-documentation/#/manage-account?id=switch-account).

1. From the side menu, click **Users > Invite Users**. An invitation link is automatically generated.  
By default, a new invitation link has a 14 days expiry date.  Whenever you invite new users, the same link will be displayed with the remaining expiry date until it expires. In the example below, SA invites a new user to SHIP-HATS. As the invite was created 2 days earlier, the link is valid for the next 12 days.

   <kbd>![Invite_users_3](Invite_users_3.png ':size=100%')</kbd>

1. Click **Email me** to send this link with the expiry date to your SHIP-HATS registered email address and forward it to the intended users so that they can provide required information in the **Invitation Form**.  
Alternatively, click the copy icon to copy and share the invite link with intended users. Note, in this case, make sure to inform the users about the expiry date of this link.

## [Create Account](#create-account)
You will receive an invitation email with a link to onboard to SHIP-HATS portal upon successful approval. 

Access the link via the onboarding email and perform the following steps based on the account that you want to create. 

### To create an account for a Public Officer:

1. In the Invitation form, select the role as **Public Officer**. 

1. Enter the following details, and then click **Submit**.  

   - **First Name:** Enter first name of the user.
   - **Last Name:** Enter last name of the user.
   - **Public Service Email Address:** Enter official email address of the user.
   - **Require SEED Account:** Select this checkbox if the user requires a SEED account. This account is required only for a user who is actively involved in development work on a non-GSIB device. For more information, refer to the [SEED](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/#/) documentation.  
<br />

   <kbd>![create_account](signing2.png ':size=100%')</kbd>

### To create an account for a Vendor:

1. In the Invitation form, select the role as **Vendor**.  

   <kbd>![create_vendor_account](new-account-vendor.png ':size=60%')</kbd>
1. Enter the following details, and then click **Submit**.  

   - **First Name:** Enter first name of the user.
   - **Last Name:** Enter last name  of the user.
   - **Company Email Address:** Enter email address of the user. 
   - **Mobile Number:** Enter mobile number of the user.
   - **Organisation:** Enter organisation name of the user. 
   - **Department:** Enter department name of the user.
   - **Require SEED Account:** Select this checkbox if the user require a SEED account. This account is required only for users who are actively involved in development work on a non-GSIB device. For more information, refer to the [SEED](https://docs.developer.tech.gov.sg/docs/security-suite-for-engineering-endpoint-devices/#/) documentation.  
<br />
   
   <kbd>![create_account](vendor3.png ':size=100%')</kbd>


## [Approve new users](#approve-new-users)
After a user submits the completed SHIP-HATS **Invitation Form**, Subscription Admin (SA) and Project Admin (PA) will be notified by an email to approve the user registration.

### To approve new user registration:
1. Log in to the [SHIP-HATS portal](https://www.ship.gov.sg/).  
   Make sure that you are in the required account. If needed, refer to [Switching account](https://docs.developer.gov.sg/docs/ship-hats-documentation/#/manage-account?id=switch-account).

   <kbd>![pending user approval notification](pending_user_approval_notification.png ':size=100%')</kbd>

   If there is a pending user approval task for you, it will be displayed in the **ALERTS** section.  

2. Click **View** corresponding to that alert. You will be directed to the **Pending Approval** section.

   >**Tip:** Alternatively, from the side menu, click **Users** > **All Users**. 
   
   If there is a pending user approval task, the **Pending** section will display the number of users pending approval. Here, you can view the users that are pending your approval along with their email address.  

   <kbd>![add user](tp-add-user.png ':size=100%')</kbd>   
    
   Only email addresses that are included in our approved list will be approved. If you provide an email address that is not included in our approved list, in the SHIP-HATS portal when approving the user, you will see a message indicating that this domain will be required to be included in TechPass. As required, you may select the **Proceed to whitelist domain** option to raise a service request. 
   
   <kbd>![unapproved_domain](vendor-unapproved-user-domain.png ':size=100%')</kbd>

3. Click **Approve** corresponding to the user.

   <kbd>![after adding user](tp-add-user-3.png ':size=100%')</kbd>

4. In **Grant user access for:**, You can choose which tools to give access to. Following options are available:
   - **CI tools:** Select this option if the user is required to have access to JIRA, Confluence, Bitbucket, Bamboo, pCloudy, SonarQube, Fortify SCA & WebInspect, and Prisma Cloud services.
   - **SonaType tools:** Select this option if the user is required to have access to Nexus Repository and Nexus IQ Scan services.  

1. Click **Confirm**.  
This user is now approved as SHIP-HATS user under this account.

   >**Note:** Irrespective of agencies, individuals approved as SHIP-HATS users can be added to any SHIP-HATS project and will be billed under the account that initially approved them.  

## [View users](#view-users)

Subscription Admin (SA) and Project Admin (PA) can view all users associated with a subscription account and their roles in your account.

### To view users:

1. Log in to the [SHIP-HATS portal](https://www.ship.gov.sg/).  
   Make sure that you are in the required account. If needed, refer to [Switching account](https://docs.developer.gov.sg/docs/ship-hats-documentation/#/manage-account?id=switch-account).

1. From the side menu, click **Users > All Users**.  
   A list of users appears, along with following details:
   Column|Description
   |---|---|
   **Name**|Indicates the name of the user. <br>If *First Name* and *Last Name* were not provided when creating a new user account, only email address will appear in this column.<br>If a user is a Subscription Admin, it is indicated by the label **Subscr Admin** beside the username.
   **Project Role**|Indicates whether a user is a Project Admin.
   **Quota consumed**|Indicates whether the user is consuming quota from the current subscription. <ul><li>If user is not consuming quota of the subscription, a tag **free user**, appears beside the name. When you hover over the tag, you can view the billing subscription under which the quota is being consumed.</li></ul>   
   **CI**| Indicates whether the user is consuming the CI tools quota from the current subscription. 
   **Sonatype**|Indicates whether the user is consuming Sonatype tools quota from the current subscription.
   **Last Login**|Indicates the date and time when the user logged in the last time.
   **Action**|Enables you to [Manage access](#manage-accessmanage-access) and [Remove User](#remove-usersremove-users).

   <kbd>![all-users-new](all-users-new.png ':size=100%')</kbd>

   You can perform following additional functions on this screen:
   - **Sort:** You can sort this list in ascending or descending order by one of the following options:
      - Name
      - Project Role
      - CI
      - Sonatype
      - Quota consumed  
      - Last Login
    - **Search:** You can quickly search for a user by typing the username in the search box.

       <kbd>![search_user](export-csv.png ':size=100%')</kbd>

    - **Download:** If you want to download the user list as a .csv file to your local machine, click **Export CSV**. This csv lists the active and removed users along with the approval and removal details. For more details, refer to the [Generate a User Report](#generate-a-user-report) documentation.

## Generate a User Report
You can generate a report to view all details for the active and removed users.

### To generate a user report:
1. Log in to the [SHIP-HATS portal](https://www.ship.gov.sg/).   
   Make sure that you are in the required account. If needed, refer to [Switching account](https://docs.developer.gov.sg/docs/ship-hats-documentation/#/manage-account?id=switch-account).
1. From the side menu, click **Users > All Users**.

   <kbd>![all-users-new](all-users-new.png ':size=100%')</kbd>

1. Click **Export CSV**.  
   The CSV report is downloaded to the your machine with the following details:

   Field|Description
   |---|---|
   **Username**|Indicates the username for the user
   **Name**|Indicates the full name of the user
   **Email**|Indicates the email address of the user
   **Subscription Admin**|Indicates whether the user is a Subscription Admin. 
   **Project Role**|Indicates whether the user is a Project Admin.
   **Quota consumed**|Indicates whether the user is consuming quota from the current subscription.  
   **CI Quota Consumed**|Indicates whether the user is consuming CI tools quota from the current subscription. 
   **Sonatype Quota Consumed**|Indicates whether the user is consuming Sonatype tools quota from the current subscription. 
   **Last Login**|Indicates the date and time when the user logged in the last time.
   **Status**|Indicates whether the user is active or removed.
   **Approved Date**|Indicates the date when the user was approved.
   **Approved By**|Indicated the name of the SA or PA who approved the user.
   **Removed Date**| Indicates the date when the user was removed.
   **Removed By**|Indicates the name of the SA or PA who removed the user.
   **Removal Reason**|Indicates the reason for removal of a user as entered by the SA or PA

## [Manage Access](#manage-access)

### To manage access for a user:

1. Log in to the [SHIP-HATS portal](https://www.ship.gov.sg/).   
   Make sure that you are in the required account. If needed, refer to [Switching account](https://docs.developer.gov.sg/docs/ship-hats-documentation/#/manage-account?id=switch-account).

1. From the side menu, click **Users > All Users**.

   <kbd>![all-users-new](all-users-new.png ':size=100%')</kbd>

1. Search for the user whose access you want to manage. 
1. From the **Action** column, click ![3_dot](3_dot.png) corresponding to the user.  
1. Select **Manage Access**, and then select the tools that you want to enable for the user. Following options are available: 
   - **CI tools:** Select this option if the user is required to have access to JIRA, Confluence, Bitbucket, Bamboo, pCloudy, SonarQube, Fortify SCA & WebInspect, and Prisma Cloud services.
   - **SonaType tools:** Select this option if the user is required to have access to Nexus Repository and Nexus IQ Scan services.

   <kbd>![manage-access](manage-access.png ':size=100%')</kbd>

1. Click **Proceed**.  
   A confirmation message appears, indicating that the user will receive an email regarding the change. 

   >**Notes:**
   >- You will be able to update access only if the numbers of users align with the approved tools quota for the users.
   >- The Proceed button is enabled only when there is a change to the existing selection.
   >- A PA or SA user will be able to update their own access.
   >- You will not be able to proceed if both the options are cleared.


## [Remove users](#remove-users)

We recommend Subscription Admin (SA) and Project Admin (PA) to periodically review the named users in their account, consumed user quota and remove users who are no longer required.

>**Note:** SA and PA can remove a user who does not have the Project Admin or Subscription Admin roles in the subscription account.

### To remove a user:

>**Notes:**
>- You can remove a user that is added to the billing subscription (quota consumed) only.
>- You can remove a user from a subscription if the user is not consuming quota from the current subscription (labeled as **free user**). However, you cannot remove a user consuming quota from current subscription if the user is also included in another subscription.
>- You cannot remove a user from a billing subscription (quota consumed) if the user is also added to another subscription (quota not consumed and labeled as **free user**). 

1. Log in to the [SHIP-HATS portal](https://www.ship.gov.sg/).   
Make sure that you are in the required account. If needed, refer to [Switch account](https://docs.developer.gov.sg/docs/ship-hats-documentation/#/manage-account?id=switch-account).
1. From the side menu, click **Users > All Users**.
1. Search for the user to be removed and from the **Action** column, click ![3_dot](3_dot.png) corresponding to the user.
   >**Tip:** Refer to [View users](#view-users) to know how to search for users and to sort by **Quota Consumed**.

   <kbd>![remove_user](remove-users-2.png ':size=100%')</kbd>

1. Choose **Remove User**.

## [Change SA](#change-sa)

To change or transfer the existing SA role to another user, one of the SAs can raise a [service request](https://jira.ship.gov.sg/servicedesk/customer/portal/11/create/364) with the required details, such as the name and email address of the user to whom the SA role is to be transferred.


## [Change PA](#change-pa)
To change or transfer the existing PA role to another user, one of the SAs can add or remove PA on the [SHIP-HATS Portal](http://www.ship.gov.sg).

### To view existing PAs:
1. Log in to [SHIP-HATS Portal](http://www.ship.gov.sg).
1. Click **Users > All users**.
1. Click **Project Role**.

   <kbd>![view user role](pa2.png ':size=100%')</kbd>

1. Name of users will be displayed based on the project role.

### To add PAs:
1. Log in to [SHIP-HATS Portal](http://www.ship.gov.sg).
1. Click **Overview** > **Project**. 

   <kbd>![overview page](overviewpage1.png ':size=100%')</kbd>
1. Click the **pencil** icon.

   <kbd>![pa](pa1.png ':size=60%')</kbd>

1. Click **+ Add another**. The number of PAs each project is entitled to is based on the [subscription tier](http://www.developer.tech.gov.sg/singapore-government-tech-stack/toolchain/subscription) quota the agency has subscribed to. 

   <kbd>![add pa](addpacopy.png ':size=60%')</kbd>

1. Choose the designated PA from the drop-down selection and click **Add**. 

   <kbd>![add pa](add-ppl.png ':size=60%')</kbd>

You have successfully added a PA.

### To remove PAs:
1. Log in to [SHIP-HATS Portal](http://www.ship.gov.sg).
1. Click **Overview** > **Project**.

   <kbd>![overview page](overviewpage1.png ':size=100%')</kbd>
1. Click the **pencil** icon.

   <kbd>![pa](pa1.png ':size=60%')</kbd>

1. Hover over to the name you would like to remove, and then click **Remove**.

   <kbd>![remove](remove-users.png ':size=60%')</kbd>

1. When prompted, click **Yes**.

   <kbd>![remove confirmation](usure.png ':size=60%')</kbd>

   You have successfully removed the user as a PA.

## [Reactivate users](#reactivate-users)

If SHIP-HATS users are inactive for 60 consecutive days, their status changes from **normal user** to **sleeping user**. If the user continues to be inactive, from day 81 onwards an email notification is sent every day to the user until user becomes active (**normal user**) or until it reaches day 90.  

On day 91, if the user is still inactive on SHIP-HATS, user status changes from **sleeping user** to **suspended user**, indicated by a grey avatar.  

<kbd>![profile-legends](profile-legends.png ':size=100%')</kbd>

<!--SA and PA can reactivate a suspended user back to their account if required.-->

### To reactivate a user:

If you are **a TechPass user**, the SA can raise a service request using the [TechPass Support form](https://form.gov.sg/#!/5f69797d0666cb0011cc59da). It will take 1-3 business days to process the service request.

If you are **not a TechPass user**, the SA or PA can complete the following steps to reactivate a user:

1. Log in to the [SHIP-HATS portal](https://www.ship.gov.sg/).  
   Make sure that you are in the required account. If needed, refer to [Switching account](https://docs.developer.gov.sg/docs/ship-hats-documentation/#/manage-account?id=switch-account).  
1.  From the side menu, click **Users > All Users**.  
1. Search for the user to be reactivated and from the **Action** column, click ![3_dot](3_dot.png) corresponding to the user.  

   <kbd>![user_status_2](user_status_2.png ':size=100%')</kbd><br />
   
   > **Tip:** Refer to [Viewing users](#view-users) to know how to search for users  

1. Choose **Reactivate User**. User, SAs and the requestor will be notified through an email about the reactivation.  

   >**Notes:**
   >- Though the reactivated user can log in using the existing credentials, we recommend reactivated users to reset their password. The email sent to the reactivated users includes the link to reset their password.  
   >- After a user has been reactivated, an email notification about this reactivation is sent to the requestor and the SAs.


<!-- CODEX-77075 -- HATS - PORTAL-1384 As a SA/PA, I would like to see the existing user groups that are assigned to related to my subscription in the menu. -->
<!--
## Manage All User Groups
An SA and PA can view and manage all the existing user groups that are assigned to their subscription. 

>**Note:** The number of user groups that you can create is same as your projects quota. 

### To access all user groups: 
1. Log in to the [SHIP-HATS portal](https://www.ship.gov.sg/). 
1. From the side menu, select **Users** > **All User Groups**.
     
   <kbd>![All User Groups]()

1. 

### To create a new user group:

1. 




-->