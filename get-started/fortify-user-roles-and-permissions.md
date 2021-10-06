# Fortify User Roles and Permissions

User roles and their permissions determine the actions a user can perform in Fortify Software Security Center (SSC). Fortify as a COTS product comes with system defined roles and permissions. We have customised these system-defined roles and permissions to meet your requirements.

The following table lists the roles and permissions available on Fortify with SHIP-HATS. The Project Admin (PA) can:

- [Assign or unassign roles to users excluding other PAs for each Fortify application](https://docs.developer.tech.gov.sg/docs/ship-hats-documentation/#/portal-guide/manage-fortify-applications?id=manage-user-role-in-fortify-applications).
- View and edit application version.
- [Remove applications](https://docs.developer.tech.gov.sg/docs/ship-hats-documentation/#/portal-guide/manage-fortify-applications?id=remove-users-from-fortify-applications).
- Increase Fortify quota.
- [Retrieve token from SHIP-HATS portal to setup Bamboo pipeline](https://docs.developer.tech.gov.sg/docs/ship-hats-documentation/#/portal-guide/manage-fortify-applications?id=get-token-for-fortify-application).

<!--Refer to **Manage user role in Fortify applications** for more information.-->

Note:

- To run dynamic scans, the user must either have a **User** or **Manager** [role in WebInspect (WIE)](https://confluence.ship.gov.sg/pages/viewpage.action?spaceKey=HATSKB&amp;title=WebInspect+User+Access+Control).
- PAs can refer to [WIE service request guidelines](https://confluence.ship.gov.sg/display/HATSKB/WebInspect+Service+Tickets+Guide) and raise service request to add users and assign roles in WIE. You can access these pages only if you have access to Confluence in your organisation.


| **Roles**     | **Permissions** |
| ------------- |:-------------|
| **Viewer**    | By default, all the users have this role in the Fortify applications they have been added to.<br /> Application users with this role can view:<br /><ul><li>General information of the application.</li><li>Application versions.</li><li>Application’s dynamic and static scan results and related issues.</li></ul>However, users who have only this role cannot:<br /><ul><li>Involve in issue triage or the remediation process.</li><li>Upload analysis results or audit issues. Audit issues here means the ability to add comments and tag issues.</li></ul>|
| **Report Uploader**      | In addition to **Viewer permissions**, users with this role can:<br /><ul><li>Generate reports.</li><li>Upload dynamic and static scan results.</li></ul>     |
| **Security Tester**      | In addition to **Viewer** and **Report Uploader** permissions, users with this role can execute dynamic scan requests such as: <br /><ul><li>Process dynamic scans.</li><li>Audit issues. In other words, in addition to viewing issues, the security tester can comment and tag issues.</li></ul>     |
|     **Security Lead**          |In addition to **Viewer**, **Report Uploader** and **Security Tester** permissions, users with this role can:<br /><ul><li>Manage reports</li><li>Suppress issues</li></ul>
