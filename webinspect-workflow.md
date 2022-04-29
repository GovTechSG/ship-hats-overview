# Workflow

**Topics**  

- [Prerequisites](#prerequisites)
- [Set up Initial Scan](#set-up-initial-scan)
- [Integrate Scans in a CI Pipeline](#integrate-scans-in-a-ci-pipeline)
- [Review Vulnerabilities](#review-vulnerabilities)

## Prerequisites

Agency and Application must onboard WIE (via HATS Service Request) to use. 

- Fortify Application & Application Version to be accessible in WIE
    - Existing Fortify Applications to use WebInspect shall be specified in the HATS Service Request
- Static URL (hostname/IP addresses) where web application will be hosted for scanning. This must be publicly accessible from Internet.
    - Specify in HATS service request to place URLs in whitelist.
    - Our outgoing IP is 18.139.238.157
- Provision WIE users to manage Fortify applications in WIE
    - Only users that want to perform scans on WIE will require a user role in WIE ([WebInspect User Access Control](webinspect-user-access-control))
    - There are two roles offered to agencies in WIE:
        - **User:** A user can perform scans, cannot delete scans.
        - **Manager:** A manager can perform and delete scans.
    - We suggest that agencies only assign **Manager** role to a maximum of 2 users whom you want to provide the *Delete* access.

## Set up Initial Scan

Configure a scan and create a reusable scan template for scanning the web app.

The initial scan setup is necessary to create a suitable configuration for scanning the Web Application and to save that configuration to be reused for repeated scans.

It is necessary to verify that the scan configuration adequately tests the Web Application (that is all endpoints are hit or pages are crawled).

This should be performed by someone intimately familiar with the Web Application under test, such as an Application Security Tester or a Security Lead.

## Integrate Scans in a CI Pipeline

You can execute repeatable WebInspect scans using the scan template and operate the [WebInspect scans via the WebInspect API](webinspect-scan-via-api).

## Review Vulnerabilities
WebInspect scan results are immediately uploaded to SSC after each run. Vulnerabilities should be reviewed and analysed directly in SSC.

>**Note:** Vulnerabilities stemming from WebInspect can be identified in SSC by the field **Analysis Type = WebInspect**.



