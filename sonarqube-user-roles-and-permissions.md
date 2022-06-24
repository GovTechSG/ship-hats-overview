# SonarQube User Roles and Permissions


The following table lists the roles and permissions available on SonarQube with SHIP-HATS. 

| **Roles**     | **Permissions** |
| ------------- |:-------------|
| **Administer** | Access project settings and perform administration tasks|
| **Administer issues**    | Change the type and severity of issues, resolve issues as being *fixed*, *won't fix*, or *false-positive*. Users also need the **Browse** permission.|
| **Administer security hotspots**      |Resolve a Security Hotspot as reviewed (fixed or safe), reset it as to review. Users also need the **Browse** permission.|
| **Browse**      |    Access a project, browse its measures and issues, confirm issues, change the assignee, comment on issues and change tags.  |
|     **Execute analysis**          |Ability to get all settings required to perform an analysis (including the secured settings like passwords) and to push analysis results to the SonarQube server.|
|**See source code**|View the project's source code. Users also need the **Browse** permission.|
