# Target

* [ ] Analyze the Target attack scenario.
* [ ] Look at the attack vulnerabilities, the cost of the breach and several prevention techniques.
* [ ] Investigate the anatomy of a Watering Hole attack.

***

## Target Attack Timeline

[In December 2013, a data breach of Target's systems affected up to 110 million customers. Compromised customer information included names, phone numbers, email and mailing addresses. In March 2015, Target reached a class-action settlement with affected consumers for $10 million (plus class-action attorney fees).](https://en.wikipedia.org/wiki/Target\_Corporation)

[In May 2016, Target settled with affected banks and credit unions for 39 million (class- action attorney fees), of which $19 million would be disbursed by a MasterCard program.](https://en.wikipedia.org/wiki/Target\_Corporation#Customer\_privacy) - Wikipedia

### Situation

> In November and December 2013, cyber thieves executed a successful cyber attack against Target, one of the largest retail companies in the United States. The attackers surreptitiously gained access to Target’s computer network, stole the financial and personal information of as many as 110 million Target customers, and then removed this sensitive information from Target’s network to a server in Eastern Europe.

> John Mulligan, Target’s Executive Vice President and Chief Financial Officer, testified that his company “had in place multiple layers of protection, including firewalls, malware detection software, intrusion detection and prevention capabilities and data loss prevention tools.”38 He further stated that Target had been certified in September 2013 as compliant with the Payment Card Industry Data Security Standards (PCI-DSS), 39 which credit card companies require before allowing merchants to process credit and debit card payments.
>
> * "Kill Chain" Analysis of the 2013 Target Data Breach; Committee on Commerce, Science and Transportation

### Kill Chain Timeline

![timeline](https://d3i71xaburhd42.cloudfront.net/42b87d76acce25631266051b02cedd88d83c5ab9/2-Figure1-1.png)

#### First Trigger - Already Compromised

* Fire eye event on Nov. 30.
  * False positive prone users do not fully trust.
* No additional activity information.
  * What traffic preceded and followed, from and to where?
* Business context of critical assets exposed?
  * Network context where attackers could reach critical assets?
* No business process for to triage and analyze was defined.
* The attack was ignored.

#### More Alerts - No Linkage

* More alerts with different areas of network.
* Not correlated with other activity or in the context of the business or network.
* Not enough visibility or context.
* Still ignored.

#### DOJ Notification - 40 million Records Gone

* Too late
* Nightmare business scenario

### Target Attack Vulnerabilities

* Attackers took advantage of weak security at a Target vendor, gaining a foothold in Target's inner network.
  * Recon
  * Weaponize
  * Deliver
* Target missed warnings from its anti-intrusion software that attackers were installing malware in its network.
  * Deliver
  * Exploit
* Attackers took advantage of weak controls within Target's network and successfully maneuvered into the network's most sensitive areas.
  * Deliver
  * Exploit
  * Install
* Target missed information provided by its anti-intrusion software about the attackers' escape plan, allowing attackers to steal as many as 110 million customer records.
  * Command & Control
  * Action

#### Cost

* May of 2017, Target to pay $18.5 million to settle claims by 47 states and the District of Columbia and resolve a multi-state investigation into a massive data breach in late 2013.
* According to the Star Tribute in 2019:
  * Target noted that it reached a settlement in a class-action lawsuit brought by banks for about $58 million in May 2016.
  * It also reached confidential settlements with major card issuers such as Visa, Mastercard, American Express, Discover as well as a number of individual banks.
  * In total, Target has reported that it incurred about $292 million in expenses related to its data brach, about 90 million of which were offset by insurance.

#### Prevention

* Security logs and events
* Network flow data
* Vulnerability data
* Network topology
* Asset profile with business context, risk, ownership
* Correlation rules
* User behavioral analysis
* Increased incident relevance
* One incident case and analysis workflow
* Integrated forensics - Rapid confirmation of attack
* Massive reduction of window exposure

## Watering Hole Attack

Watering Hole : The attacker compromises a site likely to be visited by a particular target group, rather than attacking the target group directly.

* July 2012, several high-profile institutions in the financial and technology sectors were victimized by a 'watering hole' attack.
* July 13-15, 2012 - Customers of the bank are redirected to a malicious download site when they visit to do their online banking.
* July 15-18, 2012 - Infections are detected at several companies.

### Vulnerable Hosts Infected

Attackers used different variants of the **Gh0st RAT** remote access Trojan horse, making detection very hard.

#### Variant A

* Exploited a known Microsoft vulnerability (CVE-2012-1889, 6/12/2012).
* Path for all Microsoft operation systems was released on 7/10/2012.
* Variant was not recognized by any AV vendor.

#### Variant B

* Exploited a known Java vulnerability (CVE-2012-1723, 6/16/2012).
* Patch was released by Oracle 6/12/2012.
* Variant was recognized by McAfee VSE as of July 2017, 2012.

### Host Response

After being infected, compromised hosts made contact with a remote command and control server in China.

* Infected machines attempt to communicate with one of two Chinese command and control (C\&C) servers, 58.64.155.57 and 58.64.155.59, on ports 53, 80, and 443.
* If communications are successfully established, the C\&C server gains complete, real-time control of a system on the protected network.
* The malware, a remote access Trojan, allows a remote attack to access data, log system activity, capture key logs, take screenshots, activate the system's camera, and record from the system's microphone.
  * The remote attacker can also drop additional downloads and programs on the controlled machine, and use it as a launching point for further attacks.

### Risk of Delayed Response to Attack

The infected machine becomes the new launch point of deepening the penetration.

* The infected machine 'legitimately' distributes more malware inside the enterprise network to gain a stronger foothold if detected.
* The malware's first goal is to obtain privileged user identities, which it then uses to gain access to valuable assets inside the enterprise network.
* Most attacks use ports and scans that typically are not executed from either the infected machines or user IDs.
* After valuable assets are found, they are slowly exfiltrated to not raise any suspicion.

## Apply Big Data to Security Intelligence and Threat Management

### Collection, Storage, and Processing

* Collection and integration
* Size and speed
* Enrichment and correlation

### Analytics and Workflow

* Visualization
* Unstructured analysis
* Learning and prediction
* Customization
* Sharing and export

### Global Intelligence

* Campaign identification
* IP reputation covering attacker, industry, and region
* Comparisons
* Anomaly detection
