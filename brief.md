Version: NAFATH-V4
Track: Cybersecurity

## Overview
A national service provider depends on software, AI models and internet routes that attackers could compromise in secret. Each of the six fields covers one part of that risk. The brief is meant to help a project manager see where compromise could happen and which controls reduce it. Software teams keep secrets out of code. AI teams must defend models against evasion and poisoning. Mobile apps can be checked against the MASVS standard. Networking uses RPKI to make route hijacking harder. Cybersecurity shows how one library flaw can spread widely, and an SBOM lists which components a system contains. Together, these controls help the provider prevent, detect and respond to supply chain attacks.

## Software
The Twelve-Factor App methodology says configuration, including credentials for external services, should be stored in environment variables rather than application code. Configuration means values that vary between deployments, such as database handles and hostnames. Keeping these values outside code lets the same codebase run in development, staging, and production. The page's test is whether the codebase could be made open source at any moment without exposing any credentials.

Resource: The Twelve-Factor App, III. Config - https://12factor.net/config

## AI
Adversarial machine-learning attacks include evasion, poisoning, and privacy attacks. Evasion occurs after training, when an attacker alters inputs to make a model produce incorrect predictions. Poisoning happens during training, when malicious data or modifications undermine the model or introduce a backdoor. Privacy attacks aim to extract information about training data or the model itself. These attacks differ in timing, target, and objective, and can affect data, model behavior, or confidentiality.

Resource: NIST AI 100-2 E2023, Adversarial Machine Learning: A Taxonomy and Terminology of Attacks and Mitigations - https://csrc.nist.gov/pubs/ai/100/2/e2023/final

## Mobile
The OWASP Mobile Application Security Verification Standard (MASVS) is a security standard from the OWASP Mobile Application Security project for Android and iOS apps. Its control groups cover storage, cryptography, authentication, network communication, platform interaction, code quality, resilience, and privacy. Testers and developers use these controls as a checklist of security requirements to verify an app. The related Mobile Application Security Testing Guide (MASTG) describes how to test each control.

Resource: OWASP Mobile Application Security Verification Standard (MASVS) - https://mas.owasp.org/MASVS/

## Networking
BGP route hijacking occurs when a network falsely announces it originates an IP prefix, so traffic may be diverted through it. RPKI lets address holders publish signed Route Origin Authorizations naming which autonomous system may originate a prefix. Routers can mark a route valid, invalid, or not found, and operators may filter invalid ones. However, RPKI origin validation does not protect against AS-in-the-middle attacks or provide any path validation. It only verifies the origin.

Resource: RFC 6811 - BGP Prefix Origin Validation - https://www.rfc-editor.org/rfc/rfc6811

## Cybersecurity
Log4Shell (CVE-2021-44228) was a flaw in Apache Log4j 2 (log4j-core). Its JNDI features did not protect against attacker-controlled LDAP endpoints, so an attacker who could control log messages could execute arbitrary code. NVD rates it CVSS 10.0 Critical: exploitable over the network, with low complexity and no privileges or user interaction. Version 2.15.0 disabled the behavior by default; 2.16.0, plus 2.12.2, 2.12.3 and 2.3.1, removed the functionality entirely.

Resource: NVD - CVE-2021-44228 Detail - https://nvd.nist.gov/vuln/detail/CVE-2021-44228

## Data
A Software Bill of Materials (SBOM) is a formal record containing the details and supply chain relationships of components used in building software. NTIA lists seven minimum data fields: supplier name, component name, component version, other unique identifiers, dependency relationship, author of SBOM data, and timestamp. It also requires automation support, meaning machine-readable formats, and defined practices such as frequency, depth, distribution, and access control.

Resource: The Minimum Elements For a Software Bill of Materials (SBOM) - https://www.ntia.gov/sites/default/files/publications/sbom_minimum_elements_report_0.pdf

## Misconception in My Track
A common belief is that Log4Shell affects every Apache logging library, including log4net and log4cxx. The correct version is that it is specific to the Java library log4j-core, in versions 2.0-beta9 through 2.15.0, excluding the security releases 2.12.2, 2.12.3 and 2.3.1. Organizations should therefore check which logging component and version they actually run, instead of assuming all logging libraries are vulnerable. Evidence: NVD, CVE-2021-44228 Detail, Description section: "this vulnerability is specific to log4j-core and does not affect log4net, log4cxx, or other Apache Logging Services projects."

## Open Question
Which Log4j versions and other dependencies does the provider actually run? I would verify this by generating an SBOM for each system and checking every component against the CISA Known Exploited Vulnerabilities catalog.
