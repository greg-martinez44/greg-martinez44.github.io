---
title: "Databricks's compliance security profile (CSP)"
date: 2024-01-07
tags:
  - databricks
  - reference
  - security
showMiniToc: false
---

## Enhanced Security & Compliance add-on

The [Enhanced Security and Compliance add-on](https://www.databricks.com/trust/security-features/protect-your-data-with-enhanced-security-and-compliance) is made up of two features: Enhanced Security Monitoring and the Compliance Security Profile.

### Enhanced Security Monitoring

The [enhanced security monitoring](https://docs.databricks.com/en/security/privacy/enhanced-security-monitoring.html) feature [hardens images](https://www.cisecurity.org/cis-hardened-images) and supplies malware and antivirus detection. It also packages security event logs along with your regular audit logs. Contextual information included in the logs makes investigations and blaming quick and easy.

The monitoring features apply to any compute resource in the classic compute plane, such as clusters and non-serverless SQL warehouses. Serverless warehouses do not have the additional monitoring features.

#### CIS Level 1 hardened images

Hardened VMs decreases the vulnerability of traditional VMs.

> Hardening limits potential weaknesses that make systems vulnerable to cyber attacks. More secure than a standard image, hardened virtual machine images help protect against denial of service, unauthorized data access, and other cyber threats.

CIS hardened images comply with CIS Benchmark recommendations that are recognized as secure by HIPAA and other cybersecurity authorities.

#### Improved monitoring with system tables

The enhanced security monitoring feature includes three monitoring agents: file integrity monitoring, antivirus/malware detection, and vulnerability scanning.

File integrity monitoring and antivirus/malware detection agents add rows in the system audit logs. They include contextual information to let auditors diagnose problems easily. A few examples topics included in the new audit rows are:

* New users added in unorthodox ways.
* Passwords/SSH keys are modified.
* `sudo` commands are executed.
* Configurations are enumerated via a program.
* Unusual outbound connections.
* Log files deleted.
* Hidden files created.
* Antivirus scans using an open source antivirus toolkit called [ClamAV](https://docs.clamav.net/).

### Compliance Security Profile

The [compliance security profile](https://docs.databricks.com/en/security/privacy/security-profile.html) conforms to the [FIPS 140-2 Level 1](https://csrc.nist.gov/pubs/fips/140-2/upd2/final) encryption standards. It enforces [Nitro VMs](https://aws.amazon.com/ec2/nitro/) that provide encryption for data at rest and in transit. It also ensures that clusters are kept up to date with automatic cluster update schedules. Finally, it enables workloads with PHI to be run on [serverless compute resources](https://docs.databricks.com/en/compute/sql-warehouse/serverless.html#serverless-sql-warehouses-support-the-compliance-security-profile-in-some-regions).

It is Databricks' "most secure baseline for the data plane" and is required to run HIPAA compliant workloads.

#### AWS Nitro machines

AWS Nitro System is a family of EC2 machines that are designed for better performance, price, and security.

> The Nitro System provides enhanced security that continuously monitors, protects, and verifies the instance hardware and firmware.  Virtualization resources are offloaded to dedicated hardware and software minimizing the attack surface. Finally, Nitro System's security model is locked down and prohibits administrative access, eliminating the possibility of human error and tampering.

## Serverless computing

Workspaces with the compliance security profile enabled can us serverless computing for HIPAA workloads. The compute resources are managed by Databricks but are marked as "SAFE" – these are physically separate machines than those used for non-compliant workspaces. The compute workloads and clusters are very contained:

> To protect customer data within the serverless compute plane, serverless compute runs within a network boundary for the workspace, with various layers of security to isolate different Databricks customer workspaces and additional network controls between clusters of the same customer.

Data is saved directly to S3 buckets in the customer's account – so there's no worry of saving sensitive data outside of the customer's organization.