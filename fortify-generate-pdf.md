# Generate PDF Report

**Topics**
- [Generate PDF Report from the fpr File](#generate-pdf-report-from-the-fpr-file)
- [Helper Scripts](#helper-scripts)
- [Additional Resources](#additional-resources)

## Generate PDF Report from the fpr File

### Prerequisites
- Ensure that have access to at least 1 project.
- Ensure that your account has the [minimum permissions](fortify-user-roles-and-permissions): *GT-Report-Upload-And-Generate-Only*

### Generate BIRT report using command line syntax:

1. After your Fortify SCA task is successful, create a Script task with the following command:

    ```
    BIRTReportGenerator -template <template_name> -source <audited_proj>.fpr -format <format> -output <report_file>
    
    Example : BIRTReportGenerator -template "Developer Workbook" -source results.fpr -format PDF -output fortify-scan.pdf
    
    -template includes the list (below) of the different format types
    -source specifies the fpr file that you have generated in your Fortify SCA task
    -format is the format of the report
    -output specifies the name of the output file for the PDF report
    ```

1. You can use the following template names for the template parameter:
    - Developer Workbook
    - DISA STIG
    - CWE Top 25 2019
    - CWE/SANS Top 25
    - FISMA Compliance
    - GDPR
    - OWASP ASVS 4.0
    - OWASP Mobile Top 10
    - OWASP Top 10
    - PCI DSS Compliance
    - DISA CCI 2
    - MISRA
    - PCI SSF Compliance

1. After the report generation task is successful, specify an artifact definition as shown below so that you can download the PDF report when your bamboo plan is complete.

    ![Edit artifact definition](hats-fortify-edit-artifact-definition.png)


## Helper Scripts

You can use [CICD helper scripts](https://bitbucket.ship.gov.sg/projects/CLGLAB/repos/cicd-helper-scripts/browse/bash/microfocus_fortify) provided by CTMO as well (Refer [upload_fortify_fpr.sh](https://bitbucket.ship.gov.sg/projects/CLGLAB/repos/cicd-helper-scripts/browse/bash/microfocus_fortify/upload_fortify_fpr.sh)) that uploads FPR file and generates PDF report.

## Additional Resources

- https://www.microfocus.com/documentation/fortify-static-code-analyzer-and-tools/2110/SCA_Help_21.1.0/index.htm#Utilities/GenBIRTReports.htm?Highlight=BIRTReportGenerator
