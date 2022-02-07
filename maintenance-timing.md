# Maintenance Timing


| Tool | Frequency/Timing | Impact to activity during this timing |
| --- | --- | --- |
| RDS: </br>Bitbucket</br>Bamboo</br>Jira</br>Confluence</br>Crowd </br>Gitlab | Daily, 2am to 3am |Database commits may fail. |
| NFS Snapshots: </br>Bitbucket </br>JIRA </br>Confluence </br>Crowd | Daily, 3am to 4am |New activity happening after the snapshot is initiated may not be included in snapshot. |
| EBS Snapshots:</br> Nexus Repo </br>Nexus IQ </br>Bamboo </br>LDAP </br>Gitlab | Daily, 3am to 4am | New activity happening after the snapshot is initiated may not be included in snapshot. |
| NFS Backup to EBS | Daily, 4am to 5am | New activity happening after the snapshot is initiated may not be included in snapshot. |
| S3 Bucket Snapshots: </br> Nexus Repo | Daily, 3am to 6am | Nexus Repo will be frozen while this is ongoing. (Read-only) |

