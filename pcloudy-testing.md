# pCloudy Testing

**Topics**
- [Automated Testing](#automated-testing)
- [Manual Testing](#manual-testing)

## Automated Testing
Please refer to [pCloudy CLI](https://confluence.ship.gov.sg/x/Foo4IQ) tool to get started with mobile automated testing.

If you need technical assistance on connecting to pcloudy devices, please raise a service request [here](https://jira.ship.gov.sg/servicedesk/customer/portal/11/create/149).

## Manual Testing
### Prerequisites
To access the [pCloudy web dashboard](https://hats.pcloudy.com), make sure you have the following:
- SHIP VPN
- Internet access and Firefox browser/ Firefox Developer Edition browser, preferably on a non-government issued laptop/ development laptop
- The required proxy configuration will be provided during on-boarding.

As the dashboard can only be accessed via the proxy:
- We strongly recommend the use of Firefox browser as it is tied to browser-level settings. If Chrome is used, it will affect the system-level settings.
- Please note that only pCloudy site will be accessible, all other Internet sites are blocked. Unauthorized access to other websites are being monitored and logged.

>**Notes:**
>- Applicable for users doing manual testing - the account password will expire every year.
>- The current video format provided is in FLV. The pCloudy team is working on making the default video format to be MP4.
>- The devices in pCloudy are not meant to be used to develop functional testing script. Please use emulators/simulators from Android Studio and Xcode for respective OS.
>- When installing an app on an iOS device the app has to be re-signed with the UDID of the device. If you are unable to do the automated resigning, then you can resign manually using the UDID. You can copy the UDID and paste it in your Apple Developer account to resign manually
>- Please raise a service ticket for us to dedicate a Linux elastic agent to your Bamboo plan. The  elastic agent dedicated would have pcloudy-cli and another required packages installed.
>- When developing your functional testing scripts with Robot Framework, please do note the versions of Python and the following packages:  
    >- Appium Server, v1.19
    >- Python, v3.8.5 and above
    >- Robot Framework, v3.2.2 OR pabot, v1.10.0

### Usage of Pabot

Pabot allows parallel execution of tests. However, there is a known issue where the path of the embedded screenshots in the log file does not align with the filepath of the screenshots taken when tests fail. They are stored under the `pabot_results/` folder instead.

We strongly encourage you to use Robot Framework i.e. `robot` command, where the screenshots are well embedded into the HTML report generated.



