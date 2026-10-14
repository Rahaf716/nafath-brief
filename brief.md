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

## Cybersecurity

## Data

## Misconception in My Track

## Open Question
