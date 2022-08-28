---
id: dk2ovi4aan6xaosldo08bfj
title: Research
desc: ''
updated: 1661233568756
created: 1660891750809
---

# Vulnerabilities 101

Cybersecurity is a big business in the modern world. The hacks we hear about in newspapers are from exploiting vulnerabilities. A part of penetration testing is knowing the skills and resources for whatever situation.

- What vulnerabilities are?
- Why is worth learning about them?
- How are vulnerabilities rated?
- Databases for vulnerability research.
- A showcase of how vulnerability research is used on ACKme's engagement.

A vulnerability is defined as a weakness or flaw in the design, implementation or behaviors of a system or application. An attacker can exploit these weaknesses to gain access to unauthorized information or unauthorized actions. The term "vulnerability" has many definitions by cybersecurity.

- NIST defines a vulnerability as "weakness in an information system, system security procedures, internal controls, or implementation that could be exploited or triggered by a threat source".
- Vulnerabilities can originate from many factors, including a poor design of an application or an oversight of the intended actions from a user.

| Vulnerability               | Description                                                                                    |
| --------------------------- | ---------------------------------------------------------------------------------------------- |
| Operating System            | Found within Operating Systems (OS) and often result in privilege escalation.                  |
| (Mis)Configuration-based    | From incorrectly configured application or service (website exposing customer details).        |
| Weak or Default Credentials | Applications and services that have default authentication credentials when installed.         |
| Application Logic           | Result of poorly designed applications.                                                        |
| Human-Factor                | Vulnerabilities that leverage human behavior such as phishing emails designed to trick humans. |

## Scoring Vulnerabilities (CVSS & VPR)

Vulnerability management is the process of evaluating, categorizing and remediating threats (vulnerabilities) faced by an organization. It is impossible to patch and remedy every single vulnerability in a network or computer system and sometimes a waste of resources.

![[vuln-assessment#common-vulnerability-scoring-system-cvss]]

### Vulnerability Priority Rating (VPR)

The VPR framework is a much more modern framework in vulnerability management - developed by Tenable, an industry solutions provider for vulnerability management.

- Framework is considered to be risk-driven; Meaning that vulnerabilities are given a score with heavy focus on the risk of vulnerability poses to the organization itself, rather than factors such as impact.
- VPR scoring takes into account the relevancy of vulnerability.
- VPR is also dynamic in scoring, where the risk that a vulnerability may pose can change almost daily as it ages.
- VPR uses a similar scoring range as CVSS. VPR does not have "None/Informational" category and the same vulnerability will have a different score.

| Rating   | Score      |
| -------- | ---------- |
| Low      | 0.1 - 3.9  |
| Medium   | 4.0 - 6.9  |
| High     | 7.0 - 8.9  |
| Critical | 9.0 - 10.0 |

| Advantages                                                                           | Disadvantages                                                                                                              |
| ------------------------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------- |
| VPR is a modern framework real-world.                                                | Not open-source like some other vulnerability management frameworks.                                                       |
| Considers over 150 factors when calculating risk.                                    | VPR can only be adopted apart of a commercial platform.                                                                    |
| Risk-driven and used by organizations to help prioritize patching vulnerabilities.   | Does not consider CIA triad; Confidentiality, integrity, and availability of data does not play a large factor in scoring. |
| Scores are not final and dynamic. Priority of a vulnerability can change as it ages. | N/A                                                                                                                        |

## Vulnerability Databases

There is a magnitude of different applications and services that will have vulnerabilities.

- There are resources that keep track of vulnerabilities for all sorts of software.
- Can use to look up existing vulnerabilities for applications discovered, specifically using these websites:
  - [NVD (National Vulnerability Database)](https://nvd.nist.gov/vuln/full-listing)
  - [Exploit-DB](https://www.exploit-db.com/)

**Vulnerability**
: Defined as a weakness or flaw in the design, implementation or behavior of a system or application.

**Exploit**
: An action or behavior that utilizes a vulnerability on a system or application.

**Proof of Concept(PoC)**
: A technique or tool that often demonstrate the exploitation of a vulnerability.

### NVD - National Vulnerability Database

A website that lists all public categorized vulnerabilities. Vulnerabilities are classified under "Common Vulnerabilities and Exposures" (CVE for short).

- CVEs have a formatting of `CVE-YEAR-IDNUMBER`.
- NVD allows to see all the CVEs that have been confirmed, using filters by category and month of submission.
- Not great when searching for vulnerabilities for a specific application or scenario.

### Exploit-DB

Exploit-DB retains exploits for software and applications stored under the name, author and version of the software or application.

- A resource that hackers can be helpful during an assessment.
- Can use to look for snippets of code (Proof of Concepts) that are used to exploit a specific vulnerability.

## Example Finding a Vulnerability

Throughout an assessment, there will often be multiple vulnerabilities to get results. In this scenario, we will leverage the "Version Disclosure" vulnerability to find out the version of an application.

- Applications and software usually have a version number such as "Apache Tomcat 9.0.17".
  - ![apache-version](https://assets.tryhackme.com/additional/vulnerability-module/vulnerabilities101/tomcat1.png)
  - ![apache-version-exploitdb](https://assets.tryhackme.com/additional/vulnerability-module/vulnerabilities101/tomcat2.png)