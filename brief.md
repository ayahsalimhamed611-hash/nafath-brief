Version: NAFATH-V4
Track: Cybersecurity

## Overview
A national service provider uses different technologies to deliver services to people every day. These may include software, AI systems, mobile applications, networks, and external libraries. If one part of the system has a security problem, it could affect other parts and put important information at risk.

In this brief, I explore six areas: Software, AI, Mobile, Networking, Cybersecurity, and Data. Although they focus on different things, they all play a role in keeping digital services safe. For example, developers need to protect passwords, mobile applications need secure connections, and cybersecurity teams need to know which software components their systems use.

The Log4Shell vulnerability is a good example of why this matters. It showed that a problem in one software library could affect many applications. Understanding these connections can help teams find weaknesses earlier and respond more effectively.

## Software
Passwords and API keys should not be written directly into application code. The Twelve-Factor App approach recommends keeping configuration values that change between environments in environment variables. For example, a developer can use different settings for testing and production without changing the code. This also helps reduce the risk of accidentally sharing sensitive information on GitHub. However, environment variables still need to be protected because storing secrets outside the code does not automatically make them secure.

Resource: The Twelve-Factor App – Config - https://12factor.net/config

## AI
Evasion and poisoning are two types of attacks against machine learning systems, but they happen at different stages. An evasion attack happens when someone changes an input to trick a model that has already been trained. Poisoning happens when an attacker introduces harmful or misleading data during training. For example, a modified email might get past a spam filter. Understanding this difference helps security teams decide whether they need to check training data, test model inputs, or both.

Resource: NIST – Adversarial Machine Learning: A Taxonomy and Terminology of Attacks and Mitigations - https://www.nist.gov/publications/adversarial-machine-learning-taxonomy-and-terminology-attacks-and-mitigations-0

## Mobile
OWASP MASVS provides security requirements that developers and testers can use to check whether mobile applications are properly protected. It covers areas such as secure data storage, authentication, encryption, and network communication. For example, when using a banking app, I would want to know whether my account information is stored safely and whether data is protected when sent to the server. MASVS explains what should be checked, while the OWASP Mobile Application Security Testing Guide helps explain how to test it.

Resource: OWASP – Mobile Application Security Verification Standard - https://mas.owasp.org/MASVS/

## Networking

## Cybersecurity

## Data

## Misconception in My Track

## Open Question
