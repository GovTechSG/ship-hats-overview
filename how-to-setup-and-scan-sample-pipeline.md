# Set up a simple pipeline to check out and scan the sample application
This tutorial is to guide you in setting up a simple pipeline using Javascript to check out and scan the sample application in SHIP-HATS.

## Continuous Integration
Continuous Integration(CI) is a software engineering approach where developers merge the code into a shared code repository and then verify by automated build and testing.

## Prerequisites
- You must have Bitbucket, Bamboo, Nexus IQ, and Nexus Repository added to your project.  If not, please contact your Project Admin to get the required access.

- You must have *write access* to the projects created on the above-mentioned tools. If not, please contact your Project Admin to get the required access.

- You must have a basic understanding of the SHIP-HATS CI Tools (Bitbucket, Bamboo, Nexus IQ, and Nexus Repository).

For more information on prerequisites, refer to:  
- [General Information on user roles and permissions](https://docs.developer.gov.sg/docs/ship-hats-documentation/#/user-roles-permissions)
- [Bitbucket user roles and permissions](https://docs.developer.gov.sg/docs/ship-hats-documentation/#/get-started/bitbucket-user-role)
- [Bamboo user roles and permissions](https://docs.developer.gov.sg/docs/ship-hats-documentation/#/get-started/bamboo-user-roles)

>**Note:** User Permissions information on Fortify, Nexus IQ, and Nexus Repository Manager will be updated soon!

## Set up Pipeline

### To set up a simple pipeline to check out and scan the sample application in SHIP-HATS:

1. Fork Repo to Bitbucket.  

    Bitbucket is a source code management tool. Source code for your application is hosted within a Bitbucket repository. A Bitbucket project contains one or more repositories.  

    Normally, an application development team will create an empty repository and check in their code. For this tutorial, we will make use of existing code. We will create a new repository by forking from another repository. 

    [![Step 1 of 6](Slide1.jpg)](https://youtu.be/y0znQiheC4Q)

    Click the image or [link](https://youtu.be/y0znQiheC4Q) to access the video.


1. Integrate Bitbucket to Bamboo. 

    As your code repo is in Bitbucket, we need to integrate it into Bamboo to allow and automate testing of the code/application. Bamboo is essentially a build tool that allows constant merging, testing of code  which allows  development teams to receive rapid feedback on their work.

    [![Step 2 of 6](Slide6.jpg)](https://youtu.be/8ky79S2YfRg)

    Click on the image or [link](https://youtu.be/8ky79S2YfRg) to access the video.

1. Add a Bamboo Trigger  

    Adding a Bamboo Trigger is required so that Bamboo is notified whenever there is a code change in any of the selected source code repositories. 

    [![Step 3 of 6](slide19.png)](https://youtu.be/LyBSH4T4Lc4)

    Click on the image or [link](https://youtu.be/LyBSH4T4Lc4) to access the video.

1. Add Bamboo Tasks  

    Adding Bamboo tasks allows the automated execution of code, steps and processes.

    [![Step 4 of 6](Slide20.jpg)](https://youtu.be/supsnqoPKqs)

    Click on the image or [link](https://youtu.be/supsnqoPKqs) to access the video.

1. Add Nexus IQ  

    Adding Nexus IQ as a Bamboo task allows the execution of vulnerability scanning for dependencies and libraries.

    [![Step 5 of 6](Slide25.jpg)](https://youtu.be/BW7_LRePBa8)

    Click on the image or [link](https://youtu.be/BW7_LRePBa8) to access the video.

1. Add Fortify SCA  

    Adding Fortify SCA as a Bamboo task allows the execution of vulnerability scanning for your source code.

    [![Step 6 of 6](Slide26.jpg)](https://youtu.be/0GAtczJpKwA)

    Click on the image or [link](https://youtu.be/0GAtczJpKwA) to access the video.

    >**Note:** As this is a sample pipeline, do reset user access and unlink the repository after completion of the tutorial.
