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
BGP hijacking happens when a network incorrectly or deliberately announces internet addresses that belong to another network. This can cause internet traffic to take the wrong path or become unavailable. RPKI helps reduce this risk by allowing address holders to publish signed Route Origin Authorizations (ROAs). These records identify which networks are allowed to announce specific IP prefixes. Network operators can then check incoming routes and reject invalid announcements. However, RPKI validates the route’s origin, not every network along its path.

Resource: IETF – RFC 6811: BGP Prefix Origin Validation - https://www.rfc-editor.org/info/rfc6811/

## Cybersecurity
Log4Shell (CVE-2021-44228) showed how one vulnerable software library could put many applications at risk. The vulnerability affected certain versions of Apache Log4j 2, a library commonly used by Java applications to record logs. Under specific conditions, attacker-controlled text could trigger a JNDI lookup and potentially allow remote code execution. To deal with this problem, organizations needed to identify affected Log4j components and update them to fixed versions. This was especially challenging because some applications included Log4j indirectly through other dependencies.

Resource: Apache Logging Services – Security Vulnerabilities - https://logging.apache.org/security.html

## Data
A Software Bill of Materials (SBOM) is a list of the components used in a software application, including third-party libraries. It helps cybersecurity teams identify which applications might be affected when a new vulnerability is discovered. According to NTIA, an SBOM should include details such as component names, versions, suppliers, and dependency relationships. For example, if a vulnerable library is found, a team can use its SBOM to check which systems depend on it. However, having an SBOM does not automatically mean the software is secure.

Resource: NTIA – The Minimum Elements for a Software Bill of Materials - https://www.ntia.gov/sites/default/files/publications/sbom_minimum_elements_report_0.pdf

## Misconception in My Track
A common misconception is that every Java application using Log4j was vulnerable to Log4Shell. At first, I thought that finding the Log4j name in an application automatically meant it was affected. However, the vulnerability (CVE-2021-44228) affected specific versions of the log4j-core component, not every application using Log4j. For example, an application using only log4j-api without log4j-core was not affected by this particular vulnerability.

This shows why checking the exact library and its version matters more than making assumptions. For cybersecurity teams, an accurate dependency list can save time and help them focus on the systems that actually need attention.

Resource: Apache Logging Services – Security Vulnerabilities - https://logging.apache.org/security.html

## Open Question
How can small cybersecurity teams quickly identify vulnerable third-party libraries in their applications, especially when those libraries are hidden inside other dependencies?
