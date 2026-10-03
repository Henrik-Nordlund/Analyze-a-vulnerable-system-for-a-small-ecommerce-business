# Vulnerability Assessment – Small E-Commerce Business

## Overview

This project documents a vulnerability assessment of a small e-commerce business whose customer and prospect data is stored on a remote MySQL database.

The assessment examines the security risks associated with making the database publicly accessible and evaluates potential threats to the confidentiality, integrity and availability of the information stored on the system.

The assessment uses **NIST SP 800-30 Rev. 1** as a reference framework and evaluates identified threat events based on likelihood and severity.

## Scenario

The assessment is based on a simulated e-commerce company with employees working remotely from different locations around the world.

The company stores information about potential customers and other business data on a remote MySQL database. The database has been publicly accessible since the company was established three years earlier.

The assessment considers the risks created by this configuration and how the organization could reduce those risks through appropriate security controls.

## Assessment Scope

The assessment focuses on risks affecting:

- **Confidentiality** – preventing unauthorized disclosure of information
- **Integrity** – preventing unauthorized modification or corruption of information
- **Availability** – maintaining access to information required for business operations
- **Access controls** – ensuring that access is limited to authorized users and systems

Physical security of the server is outside the scope of the assessment.

## Methodology

The assessment uses **NIST SP 800-30 Rev. 1** as a reference for the risk analysis.

The assessment identifies:

- Threat sources
- Threat events
- Likelihood
- Severity
- Overall risk

Risk is calculated as:

**Risk = Likelihood × Severity**

The resulting score is used to compare the relative significance of the identified risks.

## Risk Assessment

| Threat source | Threat event | Likelihood | Severity | Risk |
|---|---|---:|---:|---:|
| External attacker | Exfiltration of sensitive information | 3 | 3 | 9 |
| External attacker | Denial-of-service attack | 2 | 2 | 4 |
| Business employees | Accidental exposure of PII | 2 | 3 | 6 |
| Unauthorized external user | Unauthorized modification of database information | 1 | 3 | 3 |

The highest assessed risk is unauthorized disclosure of sensitive information through data exfiltration. The assessment also identifies risks related to service availability, accidental disclosure of PII and unauthorized modification of database information.

## Key Findings

The assessment identified several security concerns associated with the public accessibility of the database:

- Public database access significantly increases the system's attack surface.
- Sensitive information should not be directly exposed to the public Internet without appropriate access controls.
- PII requires protection against unauthorized disclosure.
- Internal users can also represent a source of security risk through accidental exposure or misuse.
- Access to information should be based on business need and appropriate authorization.

## Remediation Strategy

In the original assessment that I conducted, I recommended several controls to reduce the identified risks.

- Restrict direct public access to the database.
- Implement network-level access controls and firewalls.
- Enforce strong authentication and multi-factor authentication.
- Implement role-based access control (RBAC).
- Apply the principle of least privilege.
- Use defense-in-depth security controls.

### Modernized Remediation Considerations

The original exercise, completed as part of the Google Cybersecurity Professional Certificate, describes the environment as a single database. In a real-world environment, the organization should first establish what digital assets and information it has, and classify the information according to its sensitivity and business requirements.

A possible four-level classification model could distinguish between:

1. **Public** – information intended for public access.
2. **Internal** – information intended for use within the organization.
3. **Confidential** – information requiring restricted access, such as customer PII or sensitive business data.
4. **Trade Secret / Highly Confidential** – particularly sensitive information requiring highly restricted, need-to-know access.

Information with different classification levels should not necessarily share the same access model. Public information may be made available through a dedicated read-only data store or application interface, while internal, confidential and highly restricted information should require increasingly restrictive authentication and authorization controls.

The organization should also maintain an **asset management register** covering its digital assets and associated information. The register should identify assets, owners, locations, information classifications and relevant access and security controls.

This provides a foundation for answering three fundamental questions:

> **What assets and information do we have?**  
> **How sensitive are they?**  
> **Who should have access to them?**

Once the assets, information classifications and access requirements have been established, the organization's external attack surface should be assessed. A basic vulnerability and service discovery scan using a tool such as **Nmap** can identify exposed ports, services and other information that can be used to guide further hardening.

A basic scan is not a substitute for a penetration test. It provides a relatively low-cost way to establish a baseline of the externally exposed attack surface and identify unnecessary exposure before more extensive security testing is considered.
## What I Learned

This project provided experience with a basic vulnerability and risk assessment workflow:

- Identifying threat sources and threat events
- Assessing likelihood and severity
- Calculating and comparing risk
- Connecting identified risks to security controls
- Applying the principle of least privilege
- Considering information classification and access requirements
- Using NIST SP 800-30 Rev. 1 as a reference for risk assessment

The exercise also enforced the importance of distinguishing between what is known and what is assumed when conducting a risk assessment. The original scenario provides no information about the organization's employees, digital assets, technical architecture, vendors or existing security controls. As a result, the assessment that I conducted can only draw conclusions within the boundaries of the information provided by the scenario.

This is an important consideration when assessing risk: recommendations should be based on available evidence and clearly identified assumptions rather than introducing unsupported details about an organization's environment.

## Original Exercise

This vulnerability assessment was originally completed in May 2024 as part of the **Google Cybersecurity Professional Certificate**.

The original exercise used a provided vulnerability assessment template and **NIST SP 800-30 Rev. 1** as a reference for the risk analysis.

The project has since been documented and refined as a standalone portfolio project. The original assessment findings are retained, while the remediation discussion has been expanded to consider information classification, asset management and differentiated access requirements.

## Report

[View the Vulnerability Assessment Report](./Vulnerability%20Assessment%20Report.md)
