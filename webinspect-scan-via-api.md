# Scan via API

**Topics**  

1. [Prerequisites](#prerequisites)
1. [Generate an Authentication Token](#generate-an-authentication-token)
1. [Get Project Version Data](#get-project-version-data)
1. [Choose a Scan Policy](#choose-a-scan-policy)
1. [Run the Scan without Login Macro](#run-the-scan-without-login-macro)
1. [Record a Login Macro](#record-a-login-macro)
1. [Create and Upload MacroData](#create-and-upload-macrodata)
1. [Run the scan with Login Macro](#run-the-scan-with-login-macro)

## Prerequisites

- WIE server has access to your website
- Your agency has completed the onboarding process for WebInspect
- Your agency has access to SHIP bamboo
- Your agency has access to Fortify SSC

For web applications that do not have a login page, follow steps 1,2,3, and 4a.

For web appications that is protected by a login page, follow steps 1,2,3,4b,5, and 6.


## Generate an Authentication Token
To authenticate with the WIE API, an authentication token is required. 

1. To generate the Authentication Token, invoke the following cURL command:

The username and password credentials are similar to your Fortify SSC credentials.

<!-- tabs:start -->
### **Command**
```
curl --location --request POST 'https://wie.hats.stack.gov.sg/wie/rest/api/v1/auth' \
--header 'Accept: application/json' \
--header 'Content-Type: application/json' \
--data-raw '{
"username": "username",
"password": "password"
}'
```
### **Sample Response**
```
{
  "data": "FORTIFYTOKEN MDA2NDMzMDMtYjQ3NC00MGg89Tg0MDYtZjNkNmU3ZmI3YTBl",
  "responseCode": 200,
  "message": null
}
```
If you do not have the following JSON response, it is likely that your user account is unauthorized to use WIE. Please go to WIE Service Tickets for more details.


<!-- tabs:end -->




## Get Project Version Data

Similar to Fortify SCA scans, before scanning the application, WebInspect needs to know the specific Application Project Version before uploading the scan results.

### To get the projectVersions ID:

1. Navigate to the application in Fortify SSC.

    <kbd>![Project Version Data](webinspect-project-version-data.png)

    Based on the browser URL above, the **projectVersions ID** is *9999*. 
    
1. Invoke the following cURL command to get the Project Version Data:

    <!-- tabs:start -->
    ### **Command**
    ```
    curl --location --request GET 'https://wie.hats.stack.gov.sg/wie/rest/api/v1/projectVersions/9999' \
    --header 'Accept: application/json' \
    --header 'Content-Type: application/json' \
    --header 'Authorization: FORTIFYTOKEN <token>'
    ```
    ### **Sample Response**
    You should get a response similar to the following response. The Project Version Data is the information bolded in black. Do store the information somewhere because we will be using it for other API calls later on.
    ```
    {
      "data": {
        "url": null,
        "project": {
          "id": 12345,
          "name": "Sample Application"
        },
        "securityGroup": {
          "id": "321g37-g31873-3h183-213j3",
          "name": "SAMPLE GROUP"
        },
        "organization": {
          "id": "u3yi3-31283-231hu-321h0",
          "name": "SAMPLE ORGANIZATION"
        },
        "permissions": {
          "PERM_SITE_CREATE": false,
          "PERM_SITE_GEN_REPORT": false,
          "PERM_SITE_DELETE": false,
          "PERM_SITE_UPDATE": true,
          "PERM_SITE_LINK_SCANS": true,
          "PERM_SITE_SCANS_CREATE": true,
          "PERM_SITE_SCHEDULED_SCANS_CREATE": false,
          "PERM_SITE_SCANS_REPEAT": true
        },
        "id": 12345,
        "name": "1.0",
        "siteId": "3Rc43121-4823-433e-ac85-h3021h120"
      },
      "links": {
        "scans": "https://wie.hats.stack.gov.sg/wie/rest/api/v1/projectVersions/9999/scans"
      },
      "responseCode": 200,
      "message": null
    }
      ```

    <!-- tabs:end -->


## Choose a Scan Policy

A Scan Policy is a collection of vulnerability checks and attack methodologies that WIE deploys against a Web application.

Based on best practices designed to test applications for the most pervasive and problematic web application security vulnerabilities, we recommend using one of the following policies with their policy ID attached.

- Choose one of the following policy ID to continue with the scan process:
    - **OWASP Top 10 2021 (2387b73d-3a5f-4700-8ff2-85135e05d659):** This policy provides a minimum standard for web application security. The OWASP Top 10 2021 represents a broad consensus about the most critical web application security flaws.
    - **SANS Top 25 (1690337d-ae32-43ea-a008-bb0959a279fc):** The SANS Top 25 Most Dangerous Software Errors provides an enumeration of the most widespread and critical errors, categorised by Common Weakness Enumeration (CWE) identifiers, that lead to serious vulnerabilities in software.
    - **Standard (cb72a7c2-9207-4ee7-94d0-edd14a47c15c):** A standard scan includes an automated crawl of the server and performs checks for known and unknown vulnerabilities such as SQL Injection and Cross-Site Scripting as well as poor error handling and weak SSL configuration at the web server, web application server, and web application layers.
- Alternatively, you can invoke the **Get Scan Policies API** using the following cURL command if you view all the available policies that WebInspect has to offer:
    <!-- tabs:start -->
    ### **Command**
    ```
    curl --location --request GET 'https://wie.hats.stack.gov.sg/WIE/REST/api/v1/policies' \
    --header 'Authorization: {{auth_token}}'
    ```
    The cURL response will return a JSON Array with over 50 scan policies, including metadata such as description and policy category. You can go ahead and choose a scan policy that suits your needs better.

    The screenshot below shows how to find the policy ID (highlighted in yellow). 

    ![Policy ID](webinspect-policy-id.png)
    <!-- tabs:end -->

## Run the Scan without Login Macro

>**Note:** If your web application is protected by a Login page, proceed to [Record a Login Macro](#record-a-login-macro).

1. Fill in the information that was bolded in previous steps and run the cURL command.
    After the scan is complete, you will be able to view the scan results in the Fortify SSC.


    <!-- tabs:start -->
    ### **Command**
    ```
    curl --location --request POST 'https://wie.hats.stack.gov.sg/wie/rest/api/v2/scans' \
    --header 'Accept: application/json' \
    --header 'Content-Type: application/json' \
    --header 'Authorization: FORTIFYTOKEN MDA2NDMzMDMtYjQ3NC00MGg89Tg0MDYtZjNkNmU3ZmI3YTBl' \
    --data-raw '{
    "name": "Sample Scan",
    "projectVersion": {"id": 12345, "name": "1.0", "siteId": "3Rc43121-4823-433e-ac85-h3021h120"},
    "overrides": {
    "startMethod": "url",
    "startUrls": [
    "https://sampleurl.com"
    ],
    "policyID": "2387b73d-3a5f-4700-8ff2-85135e05d659" }

    }'
    ```
    After running the API call, you should receive a response with a responseCode of 201 indicating that the resource (scan) is created. 

    >**Note:** Even though the scan is created, the scan may take awhile to start depending on the number of pending scans in the queue.

    <!-- tabs:end -->


## Record a Login Macro
For web applications that have a login form, WebInspect will require a login macro to be created to crawl the website.

You should be redirected to the page below. Click Download WIE Desktop Application and after it has successfully downloaded, go ahead and install it.

To create a macro, users will need to download a standalone Windows program to record the macro manually, and upload to the WIE server via an API call.

1. Downloading and installing WIEDesktop.exe
Do note that WIEDesktop.exe only supports Windows. Head over to https://wie.hats.stack.gov.sg and login with your Fortify SSC credentials.

You should be redirected to the page below. Click Download WIE Desktop Application and after it has successfully downloaded, go ahead and install it.


2. Starting up WIEDesktop.exe
After installing WIEDesktop, Click on Guided Scan.



You will see that Windows is asking permission to open WIEDesktop.exe. Go ahead and click Open link.



Once the program is opened, select Create a Standard Web Site Scan option.



Fill in the Start URL with the URL which you want to create a login macro for. For demo purpose, I will leave it as it is.



After filling in the URL, click on Application Authentication (highlighted in yellow) and you would see that the page on the right is prompting for a login macro.

Click Create to create a new macro. This will launch another window (Truclient) in which we will start our recording process.



Once Truclient is launched, you would notice that there are two panels in the foreground. The panel on the left contains controls that would help you record the macro. The panel on the right contains the browser in which the recording will be performed.



Click the record button annotated in red, to start recording.



You should see that on the left, the first action of navigating to the URL has been detected. You can also see at the bottom that it is recording.



Go ahead and login as you could for a normal user. Do note that the entire login macro file will be encrypted, therefore there is no risk of your credentials being compromised.

You should also see your actions being populated on the left panel.



Once you have login successfully, do a quick check to see that all the actions are correctly populated. Once done, click the Stop button annotated in red.



The Stop button should be greyed out as shown below. You would need to click the Replay button in order for the login macro to do a verification check.



Upon completing the replay, the macro would require final step to verify that it has successfully reached a "login" state. As shown in the instruction below, you would need to select a new object on the right panel - annotated in green to make sure that the macro knows that the login condition has been fulfilled.

For this demo, I clicked on the accounts panel. Depending on how your website is designed, you would need to click on an object on the website that is only shown when the user has logged in.



Upon clicking an object on the right panel, you would see on the bottom left that the macro is now trying to automatically detect logout conditions. Do give it sometime to allow the macro to finish up the process.



Once it is done, it will say Successfully created an automatic logout condition.



Do click Save As to ensure that the login macro is successfully saved so that you can manually upload it for API scans in the future.



Save the login macro at any location and name the macro accordingly.



Once it has successfully saved, click the close button.



The login macro has successfully been created and reflected on WIEDesktop application.

## Create and Upload MacroData

This step is only essential if the web application has a login form. Please take a look at 4b. Recording a Login Macro if you have not done so.

1. Creating MacroData for a Project
Run the following cURL request to create MacroData for your project. The values of {{auth_token}} and {{projectVersion_data}} are created in Steps 1 and 2 respectively.

<!-- tabs:start -->
### **Command**

### **Sample Response**

<!-- tabs:end -->
curl --location --request POST 'https://wie.hats.stack.gov.sg/wie/rest/api/v1/macros' \
--header 'Accept: application/json' \
--header 'Content-Type: application/json' \
--header 'Authorization: {{auth_token}}' \
--data-raw '{
"name": "Test Macro",
"projectVersion": {"id": 12345, "name": "1.0", "siteId": "3Rc43121-4823-433e-ac85-h3021h120"}
}'

Sample Response

You should receive a response like this. Do note that even though MacroData is created, the contents of the MacroData is not uploaded yet.

Take note of the id  value as we will be using it for the uploading of MacroData.

{
  "data": {
    "id": "87uu1b26d-5ca3-4d50-b011-c1e930bce0981",
    "name": "Test Macro",
    "lastUpdatedDate": "0001-01-01T00:00:00",
    "project": null,
    "projectVersion": {"id": 12345, "name": "1.0", "siteId": "3Rc43121-4823-433e-ac85-h3021h120"},
    "securityGroup": null,
    "organization": null
  },
  "responseCode": 201,
  "message": null
}

2. Uploading MacroData to the Project
Once a MacroData is created for the Project, what is left to do is to upload to contents of the Macro you have created in 4b. Recording a Login Macro.

We will use the id  value generated in the previous step as reference to tell the server where we want the MacroData to be uploaded to.

Under --form  we will reference to absolute path of the Macro we have created in Step 4b. For our example, we assume that the webmacro we created was saved at C:/Users/Guest/Desktop/webmacro.webmacro

Run the cURL command below.

<!-- tabs:start -->
### **Command**

### **Sample Response**

<!-- tabs:end -->

curl --location --request POST 'https://wie.hats.stack.gov.sg/wie/rest/api/v1/macros/87uu1b26d-5ca3-4d50-b011-c1e930bce0981/macroData' \
--header 'Accept: application/json' \
--header 'Content-Type: multipart/form-data' \
--header 'Authorization: FORTIFYTOKEN {{auth_token}}' \
--form 'data=@/C:/Users/Guest/Desktop/webmacro.webmacro'

Sample Response

You should receive a responseCode of 201 to show that the resource is successfully created. Do remember the values of your macro ID and macro name as they will be used in the final step.

{
  "data": null,
  "responseCode": 201,
  "message": null
}

Congratulations! You are now ready to run a scan using your newly created Login Macro!

## Run the scan with Login Macro

Once you have completed steps 1,2,3,4a and 5, you are ready to run your scan. Fill in the information that was bolded in previous steps and run the cURL command.
<!-- tabs:start -->
### **Command**

### **Sample Response**

<!-- tabs:end -->
curl --location --request POST 'https://wie.hats.stack.gov.sg/wie/rest/api/v2/scans' \
--header 'Accept: application/json' \
--header 'Content-Type: application/json' \
--header 'Authorization: FORTIFYTOKEN MDA2NDMzMDMtYjQ3NC00MGg89Tg0MDYtZjNkNmU3ZmI3YTBl' \
--data-raw '{
"name": "Sample Scan",
"projectVersion": {"id": 12345, "name": "1.0", "siteId": "3Rc43121-4823-433e-ac85-h3021h120"},
"overrides": {
"startMethod": "url",
"startUrls": [
"https://sampleurl.com"
],
"policyID": "2387b73d-3a5f-4700-8ff2-85135e05d659",

"macroFileID": "87uu1b26d-5ca3-4d50-b011-c1e930bce0981",

"macroName": "Test Macro"

}

}'



After running the API call, you should receive a response with a responseCode of 201 indicating that the resource (scan) is created. Do note that even though the scan is created, the scan may take awhile to start depending on the number of pending scans in the queue.

After the scan is completed, you will be able to see the scan results in the Fortify SSC.