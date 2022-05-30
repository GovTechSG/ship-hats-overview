# SHIP-HATS Cleanup Policy for Nexus Repository

## About this document

This section provides an overview on SHIP-HATS cleanup policy for your Nexus Repositories and recommendations that you can follow to improve performance and maintenance.

## Audience

SHIP-HATS users

## Why do we need a cleanup policy?

A cleanup policy helps to purge unnecessary components to optimise disk space supporting better performance. SHIP-HATS leverages upon [Sonatype's Cleanup feature](https://help.sonatype.com/repomanager3/repository-management/cleanup-policies) to manage components at repository level.

## SHIP-HATS cleanup policy

Our default cleanup policy is configured to automatically delete a component from your nexus repository after 180 days from the date of its creation. Our cleanup policy is at repository level and not at subscription/billing account level.

This policy is applied to your repositories from October 11 2021, and the task is scheduled to run daily at 01.00 AM.

We highly recommend you to periodically review your repositories and to maintain them from your end.

## FAQs

<details>
 <summary> <b>Will there be any customer impact when the cleanup task is running?</b> </summary><br>No, there will be no customer impact.
</details>
<br>
<details>
 <summary> <b>What should I do if I wish to retain some of my artifacts of a repository beyond 180 days?</b> </summary><br>Raise a service request to SHIP-HATS with your requirements.
</details>
<br>
<details>
 <summary> <b>Can I have my own cleanup policy?</b></summary><br>
   Yes. Raise a service request to SHIP-HATS with your requirements.
</details>
<br>
<details>
 <summary><b>How to check which of our repositories are using the maximum space?</b></summary><br>
   Contact your repo administrator to get this information.
</details> 
<br>
<details>
 <summary> <b>Will there be any communications sent to agencies for the cleanups?</b> </summary><br>
   There was an initial communication sent to our tenants on September 24, 2021 about SHIP-HATS cleanup policy. As this is a recurring task scheduled every day at   01:00 AM, there will be no ongoing communications.
</details>