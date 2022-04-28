# Plugin Review Process

>**Important:** This document is provided for information only. The information contained herein is subject to change and the plugins can be rejected at ship’s own discretion

## Minimum requirement for a plugin request

- Data center approved
- *Cloud Supported
- Atlassian endorsed as Trusted Partners
  - *Cloud Fortified
  - *Cloud Security Participant
- Plugin Ratings:
  - Stars > 3
  - Votes > 50
- Vendor Supported

*Not applicable to Bamboo


```mermaid
graph TD
A(Plugin Request) -->|Text| B(Round)
B --> C{Decision}
C -->|One| D[Result 1]
C -->|Two| E[Result 2]
```

```mermaid
graph TD
A(Plugin Request) --> B{Plugin Evaluation: Data centre approved?}
B --> |Yes| C{Plugin Evaluation: Cloud Supported}
C --> |Yes| D{Plugin Evaluation: Atlassian Endorsed as Trusted Partner?}
D --> |Yes| E{Plugin Evaluation: Review Stars > 3}
E --> |Yes| F{Plugin Evaluation: Votes > 50}
F --> |Yes| G{Plugin Evaluation: Vendor Supported}
G --> |Yes| H(Plugin Installed and Tested in Dev Env)
H --> I{Dev testing OK?}
I --> |Yes| J(Install Trial Version > 1 month)
J --> K{Get Tenants Feedback (Good/Bad)}
K --> |Good| L(Cost, Budget, and Legal Review)
L --> |Passed| M(Purchasing og Plugin)
```