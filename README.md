# Vulnerability Assessment – Small E-Commerce Business

## Overview

Kort beskrivning av projektet och vad assessmenten undersöker.

## Scenario

Kort sammanfattning av scenariot:
- E-commerce company
- Remote employees worldwide
- Customer/prospect data stored on a remote MySQL database
- Database publicly accessible since company launch
- Assessment focuses on the resulting security risks

## Assessment Scope

- Confidentiality
- Integrity
- Availability
- Access controls
- Excludes physical security

## Methodology

- NIST SP 800-30 Rev. 1
- Threat sources
- Threat events
- Likelihood
- Severity
- Risk = Likelihood × Severity

## Risk Assessment

| Threat source | Threat event | Likelihood | Severity | Risk |
|---|---|---:|---:|---:|
| External attacker | Exfiltration of sensitive information | 3 | 3 | 9 |
| External attacker | Denial-of-service attack | 2 | 2 | 4 |
| Business employees | Accidental exposure of PII | 2 | 3 | 6 |
| Unauthorized external user | Unauthorized modification of database information | 1 | 3 | 3 |

## Key Findings

Kort om de viktigaste observationerna:
- Public database access creates significant exposure.
- PII requires protection against unauthorized disclosure.
- Excessive network accessibility increases attack surface.
- Both external and internal threats need to be considered.

## Remediation Strategy

Kort sammanfattning av föreslagna kontroller:
- Restrict direct public access to the database
- Network-level access controls / firewall
- Strong authentication and MFA
- Role-based access control
- Least privilege
- Defense in depth

## What I Learned

Vad projektet visar att du kan:
- identify threat sources and threat events
- assess likelihood and severity
- calculate and prioritize risk
- connect identified risks to security controls
- use NIST SP 800-30 as a risk-assessment framework

## Original Exercise

This vulnerability assessment was originally completed as part of the Google Cybersecurity Professional Certificate and has been documented here as a standalone portfolio project.

## Report

[View the Vulnerability Assessment Report](./Vulnerability%20Assessment%20Report.md)
