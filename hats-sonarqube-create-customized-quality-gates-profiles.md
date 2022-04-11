# Create Customized Quality Gates and Profiles



## Requirements to create quality gate

To create a customized quality gate and profile:
1. Raise a ticket
[here](https://jira.ship.gov.sg/servicedesk/customer/portal/11/create/149). Provide the following details:  
    a.  Quality Gate Name

    b. Quality Gate Metrics requirements (refer to [Section 2](#CreatingcustomizedQualityGatesandProfil) below)

    c. Applications to assign gates to

    d. Project Owner name and Agency name to seek approval from

2. After the Agency or Project Owner approves, we will create the gates and assign to the applications.

>**Note:** Customized profiles are not following the
standards set by the CTMO team in GovTech. Therefore, Agency will need to understand the risks and quality differences set by the new customized Quality gates.

An example of metrics required.

![Table Description automatically
generated](media/image1.png){width="6.509027777777778in"
height="3.902083333333333in"}

## Sample metric tables

The following 2 tables (**Conditions on New Code** & **Conditions on Overall Code**) can copied and paste to the ticket that is going to be raised. Thereafter, you may customize the metrics by removing those rows which **metrics** are not needed and updating the **value** to your desired value.


Conditions on New Code
-------------------------------------------------------------------------------------
| **Metric_id** | **Metric** | **Operator** |  **Value** |
| --- | --- | --- | --- |
| test | Test | Test | Test | 
| new_technical_debt | Added Technical Debt | is greater than | 1min |  


  new_branch_coverage                  Condition Coverage    is less than   2.00%

  new_conditions_to_cover              Conditions to Cover   is greater     3
   than           

  new_coverage                         Coverage              is less than   4.00%

  new_duplicated_blocks                Duplicated Blocks     is greater     5
   than           

  new_duplicated_lines_density         Duplicated Lines (%)  is greater     6.00%
   than           

  new_duplicated_lines                 Duplicated Lines      is greater     7  than           

  new_line_coverage                    Line Coverage         is less than   8.00%

  new_lines_to_cover                   Lines to Cover        is greater     9 
  new_maintainability_rating           Maintainability       is worse than  A
   new_blocker_violations               Blocker Issues        is greater     10
  new_bugs                             Bugs                  is greater     11
  new_code_smells                      Code Smells           is greater     12
  new_critical_violations              Critical Issues       is greater     13
  new_info_violations                  Info Issues           is greater     14
new_violations                       Issues                is greater     15
 new_lines                            Lines                 is greater     16 
  new_major_violations                 Major Issues          is greater     17
                                                             than           

  new_minor_violations                 Minor Issues          is greater     18
                                                             than           

  new_vulnerabilities                  Vulnerabilities       is greater     19
                                                             than           

  new_reliability_rating               Reliability Rating    is worse than  B

  new_reliability_remediation_effort   Reliability           is greater     20min
                                       Remediation Effort    than           

  new_security_hotspots_reviewed       Security Hotspots     is less than   21.00%
                                       Reviewed                             

  new_security_rating                  Security Rating       is worse than  C

  new_security_remediation_effort      Security Remediation  is greater     22min
                                       Effort                than           

  new_security_review_rating           Security Review       is worse than  D
                                       Rating                               

  new_sqale_debt_ratio                 Technical Debt Ratio  is greater     23.00%
                                                             than           

  new_uncovered_conditions             Uncovered Conditions  is greater     24
                                                             than           

  new_uncovered_lines                  Uncovered Lines       is greater     25
                                                             than           
  -------------------------------------------------------------------------------------

**Conditions on Overall Code**

  ----------------------------------------------------------------------------------------
  **Metric_id**                              **Metric**         **Operator**   **Value**
  ------------------------------------------ ------------------ -------------- -----------
  blocker_violations                         Blocker Issues     is greater     26
                                                                than           

  bugs                                       Bugs               is greater     27
                                                                than           

  classes                                    Classes            is greater     28
                                                                than           

  code_smells                                Code Smells        is greater     29
                                                                than           

  cognitive_complexity                       Cognitive          is greater     30
                                             Complexity         than           

  comment_lines                              Comment Lines      is less than   31

  comment_lines_density                      Comments (%)       is less than   32.00%

  branch_coverage                            Condition Coverage is less than   33.00%

  conditions_to_cover                        Conditions to      is greater     34
                                             Cover              than           

  confirmed_issues                           Confirmed Issues   is greater     35
                                                                than           

  coverage                                   Coverage           is less than   36.00%

  critical_violations                        Critical Issues    is greater     37
                                                                than           

  complexity                                 Cyclomatic         is greater     38
                                             Complexity         than           

  directories                                Directories        is greater     39
                                                                than           

  duplicated_blocks                          Duplicated Blocks  is greater     40
                                                                than           

  duplicated_files                           Duplicated Files   is greater     41
                                                                than           

  duplicated_lines                           Duplicated Lines   is greater     42
                                                                than           

  duplicated_lines_density                   Duplicated Lines   is greater     43.00%
                                             (%)                than           

  effort_to_reach_maintainability_rating_a   Effort to Reach    is greater     44min
                                             Maintainability    than           
                                             Rating A                          

  false_positive_issues                      False Positive     is greater     45
                                             Issues             than           

  files                                      Files              is greater     46
                                                                than           

  functions                                  Functions          is greater     47
                                                                than           

  generated_lines                            Generated Lines    is greater     48
                                                                than           

  generated_ncloc                            Generated Lines of is greater     49
                                             Code               than           

  info_violations                            Info Issues        is greater     50
                                                                than           

  violations                                 Issues             is greater     51
                                                                than           

  line_coverage                              Line Coverage      is less than   52.00%

  lines                                      Lines              is greater     53
                                                                than           

  ncloc                                      Lines of Code      is greater     54
                                                                than           

  lines_to_cover                             Lines to Cover     is greater     55
                                                                than           

  sqale_rating                               Maintainability    is worse than  A
                                             Rating                            

  major_violations                           Major Issues       is greater     56
                                                                than           

  minor_violations                           Minor Issues       is greater     57
                                                                than           

  open_issues                                Open Issues        is greater     58
                                                                than           

  projects                                   Project branches   is greater     59
                                                                than           

  reliability_rating                         Reliability Rating is worse than  B

  reliability_remediation_effort             Reliability        is greater     1h
                                             Remediation Effort than           

  reopened_issues                            Reopened Issues    is greater     61
                                                                than           

  security_hotspots_reviewed                 Security Hotspots  is less than   62.00%
                                             Reviewed                          

  security_rating                            Security Rating    is worse than  C

  security_remediation_effort                Security           is greater     1h 3min
                                             Remediation Effort than           

  security_review_rating                     Security Review    is worse than  D
                                             Rating                            

  skipped_tests                              Skipped Unit Tests is greater     64
                                                                than           

  statements                                 Statements         is greater     65
                                                                than           

  sqale_index                                Technical Debt     is greater     1h 6min
                                                                than           

  sqale_debt_ratio                           Technical Debt     is greater     67.00%
                                             Ratio              than           

  uncovered_conditions                       Uncovered          is greater     68
                                             Conditions         than           

  uncovered_lines                            Uncovered Lines    is greater     69
                                                                than           

  test_execution_time                        Unit Test Duration is greater     70ms
                                                                than           

  test_errors                                Unit Test Errors   is greater     71
                                                                than           

  test_failures                              Unit Test Failures is greater     72
                                                                than           

  test_success_density                       Unit Test Success  is less than   73.00%
                                             (%)                               

  tests                                      Unit Tests         is less than   74

  vulnerabilities                            Vulnerabilities    is greater     75
                                                                than           

  wont_fix_issues                            Won\'t Fix Issues  is greater     76
                                                                than           
  ----------------------------------------------------------------------------------------
