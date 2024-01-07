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

The [enhanced security monitoring](https://docs.databricks.com/en/security/privacy/enhanced-security-monitoring.html) feature hardens images and supplies malware and antivirus detection. It also packages security event logs along with your regular audit logs. Contextual information included in the logs makes investigations and blaming quick and easy.

### Compliance Security Profile

The [compliance security profile](https://docs.databricks.com/en/security/privacy/security-profile.html) conforms to the [FIPS 140-2 Level 1](https://csrc.nist.gov/pubs/fips/140-2/upd2/final) encryption standards. It enforces [Nitro VMs](https://aws.amazon.com/ec2/nitro/) that provide encryption for data at rest and in transit. It also ensures that clusters are kept up to date with automatic cluster update schedules. Finally, it enables workloads with PHI to be run on [serverless compute resources](https://docs.databricks.com/en/compute/sql-warehouse/serverless.html#serverless-sql-warehouses-support-the-compliance-security-profile-in-some-regions).

It is Databricks' "most secure baseline for the data plane" and is required to run HIPAA compliant workloads.

## Serverless computing

Workspaces with the compliance security profile enabled can us serverless computing for HIPAA workloads.