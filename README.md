Project Overview This project demonstrates a DevSecOps approach to cloud security. It deploys a purpose-built vulnerable web architecture (OWASP Juice Shop) using AWS CloudFormation to simulate real-world attack vectors.

Key Capabilities:

Infrastructure as Code: Complete network and application stack defined in YAML.

Threat Detection: Integrated AWS GuardDuty to monitor for malicious activity and credential exfiltration.

Automated Response: Implements an Event-Driven Architecture (EDA) using EventBridge and Step Functions to automatically isolate compromised resources and revoke IAM privileges within seconds of detection.
