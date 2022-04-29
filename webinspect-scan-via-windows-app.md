# Scan via Windows App (WIEDesktop.exe)

**Topics**  

- [Prerequisites](#prerequisites)
- [Create a Scan](#create-a-scan)
- [Verify a Scan](#verify-a-scan)
- [Create a Scan Template](#create-a-scan-template)
- [Resources](#resources)

## Prerequisites
Web Application to test must be hosted, running and accessible via Internet. It is highly recommended that a static IP is used.
The WebInspect Desktop App is installed (available for download from WebInspect Portal, 64-bit Windows only)


To log in to WIE in the desktop app, use the following details:
- **URL:** https://wie.hats.stack.gov.sg/
- **User Name:** *SHIP_username*
- **Password:** *SHIP_password*

## Create a Scan
To start a scan, click on "Guided Scan" under the ACTIONS panel on the website. It should prompt you to open WIEDesktop.exe (Desktop App)

Using the Desktop App, create a new scan using the predefined template for 'Create a Thorough Web Site Scan' and follow the guided steps.
Points to note:

Scan Type: Use scan type 'Standard' to crawl and audit the site.
Policy: This defines the type of checks to be done. For a general purpose scan, its recommended to use the 'Standard' policy (See also: 3. Choosing a Scan Policy)
Login: A login macro will be required for applications that require authentication.
The application will guide through the creation of a new login macro using the TruClient software (installed with WIE Desktop).

## Verify a Scan
Check the results of the scan to ensure that it has been configured correctly, i.e, all pages were able to be crawled

View the results of the scan. Scan results can be accessed via the WebInspect Portal under 'Scans' → 'View' → 'Scan Visualization'


Examine the site map in the results to ensure that all pages have been crawled. (If a login macro is used, also verify that authenticated pages were successfully crawled)



## Create a Scan Template
This is an optional step. You can complete this step for for repeated execution of scans. After verifying that the scan is successful create a scan template from the scan, so that it may be reused for future, automated scans.

On the WebInspect Portal, create a Scan Template based on the completed scan




Finding the Scan Template ID
All templates (that are visible to your account) can be accessed via the menu item 'Scan Templates'


Click on the template of interest - the ID will be visible in the URL parameters


Note that scan templates are by default specific to a Application + Application Version, e.g. the pictured template can only be used to create scans for 'ctmowie - 1.0'.

To scan a new application version, e.g. 'ctmowie - 1.1', a new scan template has to be created.

## Resources
- Fortify WebInspect User Guide: https://www.microfocus.com/documentation/fortify-webinspect/2010/WI_Help_20.1.0/index.htm
- All Fortify WebInspect (20.1.0) Documentation: https://www.microfocus.com/documentation/fortify-webinspect/2010/
- All Fortify WebInspect Enterprise (20.1.0) Documentation: https://www.microfocus.com/documentation/fortify-webinspect-enterprise/2010/