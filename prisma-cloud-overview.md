# Prisma Cloud (previously Twistlock)

Prisma Cloud is a container vulnerability scanner that protects custom container images, configured by subscribers.

For more information on Prisma Cloud, refer to https://docs.paloaltonetworks.com/prisma/prisma-cloud.html

**Topics**  

- [Retrieve Prisma Cloud Token](#retrieve-prisma-cloud-token)
- [Image Scan for Bamboo](#image-scan-from-bamboo)

## Retrieve Prisma Cloud Token

### Prerequisites 
- A container scanner app must already exists
- The user must be at least a Project Admin (PA).

### To retrieve Prisma Cloud token:

1. Log in to the [SHIP-HATS](www.ship.gov.sg) portal as a Project Admin.
1. Go to **Projects** > **All Projects**.

    <kbd>![Manage Projects](prisma-cloud-all-projects.png ':size=100%')
1. Select your project, and then select **Manage**.
1. Click **QA & Security**.

    <kbd>![QA & Security](prisma-cloud-qa-sec.png ':size=100%')
1. Click **Add new QA & Security tool** at the end of the page, and then select **Container Image Scanner** in the drop-down list.

    <kbd>![](prisma-cloud-add-tool.png ':size=100%')</kbd>
1. Select **Scanner type**, and then enter the **App name**.

    <kbd>![Scanner](prisma-cloud-app-name.png ':size=100%')
1. Click **Manage**.

    <kbd>![Manage](prisma-cloud-qa-sec-manage.png ':size=100%')
1. Under **Manage Tool**, select **Token for bamboo pipeline**.
1. Under **Container Image Scanner App**, select the app for which you want to retrive the token. 
1. Under **Token**, copy the token.

    <kbd>![Token for bamboo pipeline](prisma-cloud-token.png ':size=100%')


## Image Scan from Bamboo

### Prerequisites
- Your bamboo plan has a HATS Linux image dedicated to it
- You have [retrieved the token](#retrieve-prisma-cloud-token) required to do image scan from bamboo.

### To configure Bamboo plan:
1. Add a script task. You can find the script content below:
    ```
    #!/bin/bash
    
    #Scan results json file output path
    OUTPATH=$(pwd)
    
    #Build or pull your own docker image for scanning
    docker pull python
    
    #Run twistlock Scan -i <Image> -t <token> -o <OutputPath>
    hatstwistcli -i python:latest -t ${bamboo.hats_twistlock_secret} -o $OUTPATH
    ```
1. Add `hats_linux_image` as a requirement to your job.
1. Add a variable for the token that you retrieved from the SHIP-HATS portal. 
1. Define an artifact for the json file to download it as an artifact.