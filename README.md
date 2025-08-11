# CST8919 – DevOps Security and Compliance Assignment 2: Cloud Service Alternatives Report

**Course**: CST8919 – DevOps Security and Compliance  
**Author**: *Shaoxian Duan*

---

## Table of Contents
1. [Introduction](#introduction)
2. [Azure Active Directory (SSO, IAM)](#azure-active-directory)
3. [Azure Monitor & Log Analytics](#azure-monitor--log-analytics)
4. [Azure Policy](#azure-policy)
5. [Defender for Cloud](#defender-for-cloud)
6. [Azure Sentinel (SIEM/SOAR)](#azure-sentinel)
7. [Conclusion](#conclusion)

---

## Introduction
This report compares key Microsoft Azure services used in the CST8919 course with their closest equivalents in Amazon Web Services (AWS) and Google Cloud Platform (GCP). The Azure services covered are Azure Active Directory (AAD), Azure Monitor & Log Analytics, Azure Policy, Defender for Cloud, and Azure Sentinel. For each service, I identify the AWS and GCP equivalents and compare them based on their overview, core features, security and compliance capabilities, pricing models, and integration for DevSecOps practices. The information is sourced from official documentation and reliable references to ensure accuracy. The goal is to provide a clear, concise comparison to aid in understanding cross-cloud capabilities for security and compliance in DevOps.

---

## Azure Active Directory (SSO, IAM)

### Equivalents
- **AWS Equivalent**: AWS Identity and Access Management (IAM) & AWS Single Sign-On (SSO)
- **GCP Equivalent**: Google Cloud Identity & IAM

### Comparison Table
| Aspect                     | Azure Active Directory (AAD) | AWS IAM & SSO | Google Cloud Identity & IAM |
|----------------------------|-----------------------------|---------------|-----------------------------|
| **Overview**               | Cloud-based identity and access management for SSO and role-based access control. | IAM for access control; SSO for centralized authentication across AWS accounts. | Unified identity platform for IAM and SSO across GCP and external apps. |
| **Core Features**          | SSO, MFA, Conditional Access, B2B/B2C identity; hybrid identity with AD Connect. | Role-based access, fine-grained policies, MFA; SSO integrates with SAML providers. | IAM roles, SSO, MFA, domain-wide delegation; integrates with Google Workspace. |
| **Security & Compliance**  | Compliance with GDPR, ISO 27001, SOC; FIPS 140-2 encryption. | GDPR, ISO 27001, SOC 1/2/3, PCI DSS; FedRAMP compliant. | GDPR, ISO 27001, SOC 2/3; HIPAA and FedRAMP support. |
| **Pricing Model**           | Free tier; Premium P1/P2 ($6-$9/user/month). | IAM free; SSO $3/user/month for enterprise apps. | Free for basic IAM; $6/user/month for Cloud Identity Premium. |
| **Integration for DevSecOps** | Integrates with Azure DevOps, GitHub Actions; supports CI/CD identity automation. | Integrates with CodePipeline, CodeCommit; IAM roles for CI/CD. | Integrates with Cloud Build, Terraform; supports automated policy enforcement. |

### Narrative Analysis
Azure AD excels in hybrid identity scenarios and enterprise SSO with rich Conditional Access policies. AWS IAM & SSO offer granular control and scalability across AWS services, but require combining services for full functionality. Google Cloud Identity integrates seamlessly with Google Workspace, ideal for smaller organizations. For DevSecOps, Azure AD’s integration with Azure pipelines is strong, AWS shines in multi-account setups, and GCP offers simplicity for automated IAM.

---

## Azure Monitor & Log Analytics

### Equivalents
- **AWS Equivalent**: Amazon CloudWatch
- **GCP Equivalent**: Google Cloud Monitoring & Logging

### Comparison Table
| Aspect                     | Azure Monitor & Log Analytics | Amazon CloudWatch | Google Cloud Monitoring & Logging |
|----------------------------|-------------------------------|-------------------|-----------------------------------|
| **Overview**               | Unified monitoring and analytics for applications, infrastructure, and logs. | Monitoring and observability for AWS resources and applications. | Monitoring and logging suite for GCP services and custom metrics. |
| **Core Features**          | Metrics, logs, alerts; Kusto Query Language (KQL); Application Insights. | Metrics, logs, alarms; Insights for log analytics; dashboards. | Metrics, logs, dashboards; Uptime Checks; Log Analytics with BigQuery. |
| **Security & Compliance**  | ISO 27001, SOC 2; encrypted log storage; RBAC for access control. | ISO 27001, SOC 1/2/3; encrypted logs; IAM-based access. | ISO 27001, SOC 2/3; encrypted logs; IAM integration. |
| **Pricing Model**           | Pay-per-GB ingested/queried; free tier for basic metrics. | Pay-per-metric, log ingestion, and API requests; free tier. | Pay-per-GB ingested/stored; free tier for basic usage. |
| **Integration for DevSecOps** | Integrates with Azure DevOps, Sentinel; supports CI/CD alerting. | Integrates with CodePipeline, Lambda; automated alerting. | Integrates with Cloud Build, BigQuery; supports SLO monitoring. |

### Narrative Analysis
Azure Monitor’s Log Analytics with KQL offers powerful query capabilities for complex environments. CloudWatch provides robust AWS-native monitoring but can be costly for high log volumes. Google Cloud Monitoring integrates well with BigQuery for analytics-driven DevSecOps. For CI/CD pipelines, Azure’s integration with Sentinel is a plus, while AWS and GCP offer strong automation for alerts and metrics.

---

## Azure Policy

### Equivalents
- **AWS Equivalent**: AWS Config & AWS Organizations SCP
- **GCP Equivalent**: Google Cloud Resource Manager & Organization Policy Service

### Comparison Table
| Aspect                     | Azure Policy | AWS Config & SCP | Google Cloud Resource Manager & Policy |
|----------------------------|--------------|------------------|---------------------------------------|
| **Overview**               | Governance tool for enforcing compliance and resource policies. | Config for resource tracking; SCP for organization-wide policies. | Centralized resource management and policy enforcement. |
| **Core Features**          | Policy definitions, compliance audits, remediation tasks. | Resource inventory, compliance rules; SCP for permission boundaries. | IAM policies, organization policies, resource hierarchy management. |
| **Security & Compliance**  | Supports GDPR, ISO 27001; audit trails for compliance. | GDPR, SOC, PCI DSS; Config Rules for compliance checks. | GDPR, ISO 27001; audit logging with Cloud Audit Logs. |
| **Pricing Model**           | Free for policy evaluation; costs tied to resource usage. | Pay-per-rule evaluation and resource tracking. | Free for basic policies; costs for audit log storage. |
| **Integration for DevSecOps** | Integrates with Azure DevOps, ARM templates; automated remediation. | Integrates with AWS Lambda, CodePipeline for automation. | Integrates with Terraform, Cloud Build; policy as code. |

### Narrative Analysis
Azure Policy excels in unified governance with built-in remediation. AWS Config and SCP split responsibilities, offering flexibility but requiring more setup. Google Cloud’s Resource Manager is simpler for smaller organizations but less feature-rich for enterprise governance. For DevSecOps, Azure Policy’s ARM integration is strong, AWS suits complex multi-account setups, and GCP is ideal for lightweight policy enforcement.

---

## Defender for Cloud

### Equivalents
- **AWS Equivalent**: AWS Security Hub
- **GCP Equivalent**: Google Security Command Center (SCC)

### Comparison Table
| Aspect                     | Defender for Cloud | AWS Security Hub | Google Security Command Center |
|----------------------------|--------------------|------------------|-------------------------------|
| **Overview**               | Cloud security posture management and threat protection. | Centralized security findings and compliance management. | Unified security and risk management platform for GCP. |
| **Core Features**          | Security recommendations, threat detection, compliance dashboards. | Aggregates findings from GuardDuty, Inspector; compliance checks. | Asset inventory, threat detection, compliance reports. |
| **Security & Compliance**  | ISO 27001, SOC, GDPR; integrates with Azure Policy. | SOC, GDPR, PCI DSS; integrates with AWS Config. | ISO 27001, SOC; integrates with Cloud IAM. |
| **Pricing Model**           | Free tier; $15/100 resources/month for advanced features. | Pay-per-finding and analysis; free tier available. | Standard tier free; Premium $300/organization/month. |
| **Integration for DevSecOps** | Integrates with Azure DevOps, Sentinel; automated workflows. | Integrates with Lambda, CodePipeline; automation via APIs. | Integrates with Cloud Build, Pub/Sub; automated alerts. |

### Narrative Analysis
Defender for Cloud offers robust CSPM and threat detection with tight Azure integration. AWS Security Hub aggregates findings across AWS services, ideal for multi-tool environments. Google SCC is cost-effective for GCP users but less mature. For DevSecOps, Defender’s Sentinel integration excels, AWS offers broad tool compatibility, and SCC suits GCP-centric workflows.

---

## Azure Sentinel (SIEM/SOAR)

### Equivalents
- **AWS Equivalent**: Amazon Security Lake & AWS Security Hub
- **GCP Equivalent**: Google Chronicle

### Comparison Table
| Aspect                     | Azure Sentinel | Amazon Security Lake & Security Hub | Google Chronicle |
|----------------------------|----------------|-----------------------------|------------------|
| **Overview**               | Cloud-native SIEM and SOAR for threat detection and response. | Security Lake for data aggregation; Security Hub for findings. | Cloud-native SIEM for security analytics and threat hunting. |
| **Core Features**          | Log analytics, playbooks, ML-based threat detection, KQL queries. | Centralized data lake, automated remediation, cross-service insights. | Petabyte-scale analytics, threat hunting, YARA-L rules. |
| **Security & Compliance**  | GDPR, ISO 27001, SOC; encrypted data storage. | GDPR, SOC, PCI DSS; data encryption at rest. | GDPR, ISO 27001; HIPAA-compliant storage. |
| **Pricing Model**           | Pay-per-GB ingested/analyzed; free tier for basic usage. | Security Lake: per-GB ingested; Security Hub: per-finding. | Flat rate based on data volume; no free tier. |
| **Integration for DevSecOps** | Integrates with Logic Apps, Azure DevOps; automated playbooks. | Integrates with Lambda, Step Functions; API-driven automation. | Integrates with Cloud Functions, BigQuery; automated workflows. |

### Narrative Analysis
Azure Sentinel provides a powerful SIEM/SOAR with KQL and playbook automation, ideal for enterprise security. Amazon Security Lake and Security Hub combine for flexible data aggregation but require integration effort. Google Chronicle excels in large-scale analytics but lacks SOAR maturity. For DevSecOps, Sentinel’s automation is strong, AWS offers flexibility, and Chronicle suits data-heavy environments.

---

## Conclusion
Azure, AWS, and GCP provide robust security and compliance services tailored to DevSecOps. Azure excels in unified integration and enterprise features, AWS offers scalability and flexibility across tools, and GCP prioritizes cost-effective analytics. For DevSecOps, choose Azure for seamless CI/CD integration, AWS for complex multi-tool setups, and GCP for lightweight, analytics-driven security. Organizations adopting multi-cloud strategies should leverage standards like OpenID Connect for identity and SIEM data portability.