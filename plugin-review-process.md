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
B --> C{Plugin Evaluation: Cloud Supported}
C --> D{Plugin Evaluation: Atlassian Endorsed as Trusted Partner?}
D --> E{Plugin Evaluation: Review Stars > 3}
C -->|Two| E[Result 2]
```