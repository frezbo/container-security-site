# Security Terms For Container People

There's quite a lot terminology which may be unfamiliar to container app developers and cluster operators. These definitions are not meant to be comprehensive (whole books have been written about some of these topics) but hopefully a useful "starter for 10".

* **CVE** - Stands for "Common Vulnerabilities and Exposures". A CVE is at term used in security to typically refer to a specific security vulnerability (For example [CVE-2020-8558](https://nvd.nist.gov/vuln/detail/CVE-2020-8558) is an issue in kube-proxy). CVEs are useful as there's a centralised database of them which can be checked by tools and people who want to do track what versions of various products are vulnerable to specific issues, making things like checking "what vulnerabilities does the installed product with version x.x have"). 

* **CVSS** - Stands for "Common Vulnerability Scoring System". This gets used alongside the CVE database to provide severity ratings for vulnerabilities. CVSS provides formulas to approxmiate the severity of an issue, although it's important to note that these scores include subjective measures. Security tooling vendors will often use these ratings as the basis for their own severity calculations.

* **Threat Model** - An important part of any security assessment is to determine what the applicable threat model is. This essentially means "who do I think is going to attack this thing, and what kind of attacks will they use". Without a good threat model it's very easy to waste money on controls you don't need and miss controls you do need. Also if you see someone making claims that something "is secure", it's obviously important to determine what it's secure from (no system is perfectly secure), so knowing the threat model that's been used is key.

* **Attack Surface** - Often gets discussed alongside threat model. If threat model is "who's attacking me", Attack surface is "where can they attack me". So for example if an attacker is coming in over the Internet, every service you have listening on the Internet is part of your attack surface. If you use cloud services, then your logins for those services are also part of your attack surface. Generally speaking, from a security point of view, the bigger the attack surface, the harder it is to secure it (you have more things to look at), so security people are generally keen on reducing that attack surface, to give them a smaller list of things to focus on.