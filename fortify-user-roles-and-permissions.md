# Fortify User Roles and Permissions

User roles and their permissions determine the actions a user can perform in Fortify Software Security Center (SSC). Fortify as a COTS product comes with system defined roles and permissions. We have customised these system-defined roles and permissions to meet your requirements.

The following table lists the roles and permissions available on Fortify with SHIP-HATS. 
<!--Refer to **Manage user role in Fortify applications** for more information.-->

| **Roles**     | **Permissions** |
| ------------- |:-------------|
| **Project Admin** | Users with this role can: <br /><ul><li>[Assign or unassign roles to users excluding other PAs for each Fortify application](https://docs.developer.tech.gov.sg/docs/ship-hats-documentation/#/manage-fortify-applications?id=manage-user-role-in-fortify-applications).</li><li>View and edit application version.</li><li>[Remove applications](https://docs.developer.tech.gov.sg/docs/ship-hats-documentation/#/manage-fortify-applications?id=remove-users-from-fortify-applications).</li><li>Increase Fortify quota.</li><li>[Retrieve token from SHIP-HATS portal to setup Bamboo pipeline](https://docs.developer.tech.gov.sg/docs/ship-hats-documentation/#/manage-fortify-applications?id=get-token-for-fortify-application).</li></ul> |
| **Viewer**    | By default, all the users have this role in the Fortify applications they have been added to.<br /> Application users with this role can view:<br /><ul><li>General information of the application.</li><li>Application versions.</li><li>Application’s dynamic and static scan results and related issues.</li></ul>However, users who have only this role cannot:<br /><ul><li>Involve in issue triage or the remediation process.</li><li>Upload analysis results or audit issues. Audit issues here means the ability to add comments and tag issues.</li></ul>|
| **Report Uploader**      | In addition to **Viewer permissions**, users with this role can:<br /><ul><li>Generate reports.</li><li>Upload dynamic and static scan results.</li></ul>     |
| **Security Tester**      | In addition to **Viewer** and **Report Uploader** permissions, users with this role can execute dynamic scan requests such as: <br /><ul><li>Process dynamic scans.</li><li>Audit issues. In other words, in addition to viewing issues, the security tester can comment and tag issues.</li></ul>     |
|     **Security Lead**          |In addition to **Viewer**, **Report Uploader** and **Security Tester** permissions, users with this role can:<br /><ul><li>Manage reports</li><li>Suppress issues</li></ul>


>**Notes:**
>- To run dynamic scans, the user must either have a **User** or **Manager** [role in WebInspect (WIE)](webinspect-user-access-control).
>- PAs can refer to [WIE service request guidelines](webinspect-service-tickets-guide) and raise service request to add users and assign roles in WIE. You can access these pages only if you have access to Confluence in your organisation.
