# week 1

### why cybersecurity matters

- average breach cost (2023): $4.35m
- 3.5m unfilled cybersecurity positions globally
- average salary for cybersecurity professionals - $100k

### 3 pillars of identity verification

- something you know
  - most common: passwords, also security questions
- something you are
  - most secure: biometrics
- something you have
  - requires physical objects/devices in user's possession (e.g. 2fa apps)

### authentication methods

- single-factor
  - most common: username & password
- 2fa
  - combine 2 verification methods (e.g. know & have)
- mfa
  - combine 3+ verification methods from different categories

### threat actors (order of seriousness)

- nation-states
- organized crime
- hacktivists
- script kiddies

### common attack types

- malware
- phishing
- ddos
- man in middle

### why ethics matter in cybersecurity

- significant access & power
- potential for good or harm
- building trust

### foundational ethical principles

- respect for privacy
- respect for property
- avoid harm
- honesty & transparency

### 1996 - cfaa (computer fraud & abuse act)

- protected computers
  - fed, financial, interstate commerce systems
- key prohibitions
  - unauthorized access, exceeding authorization, causing damage
- severe penalties
  - criminal & civil consequences

### dmca (digital millennium copyright act)

- purpose
  - protects copyrighted works in digital age
- anti-circumvention
  - prohibits bypassing technological protection measures
- anti-trafficking
  - bans creating/distributing circumvention tools
- research exemptions
  - limited protections for good faith security research

### responsible vulnerability disclosure

- discovery & verification
  - confirm vulnerability exists without causing damage or exfiltrating sensitive data beyond what's necessary for proof
- private notification
  - contact vendor through appropriate channels with clear, actionable details about vulnerability
- collaboration & remediation
  - allow vendor reasonable time (30-90 days) to develop & release a patch
- coordinated public disclosure
  - once fixed/after agreed deadline, coordinate release of info to help users patch & share knowledge

### disclosure approahces

| responsible disclosure                                                                                                                              | full disclosure                                                                                                                                               | nondisclosure/private sale                                                                                                                            |
| --------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------- |
| balances info sharing & harm prevention. vulnerability privately reported to vendors w reasonable time allowed for fixes before public announcement | immediate public release of vulnerability details without prior vendor notification or patching opportunity. can be reckless & puts users at significant risk | finding vulnerabilities & either not reporting or selling on dark markets. generally considered unethical & often illegal                             |
| protects users by ensuring patches available before vulnerabilities become wildly known, while still allowing knowledge sharing after remediation   | systems remain vulnerable during period between disclosure & patching, creating windows of opportunity for attackers                                          | bug bounty programs offer ethical alternative, providing rewards for researchers who find & properly report vulnerabilities through defined processes |

### nist csf 2.0

- voluntary framework that provides guidance for orgs to manage & reduce cybersecurity risk. extremely popular in public & private sectors
- organizes security into 6 functions
  - govern - establish, communicate, & monitor risk mgmt strategy, expectations, & policy
  - identify - understand assets, risks, & data
  - protect - safeguard critical services
  - detect - implement activities to identify occurrence of cybersecurity event
  - respond - take action once incident detected
  - recover - implement plans for resilience & to restore capabilities after incident

### iso/iec 27001

- formal internatl standard that specifies requirements for establishing, implementing, maintaining, continually improving info security mgmt system (isms)
- key feature: cert
  - unlike nist csf, org can undergo formal audit by an accredited body to become iso 27001 cert'd
  - cert globally recognized, demonstrates formal commitment to infosec mgmt
- structure: includes mandatory clauses for isms & "annex a", which lists comprehensive set of security controls from which orgs can select to mitigate risks

### why use them?

- provides common language
- structured risk mgmt
- due diligence
- compliance w other regulations
- improves security posture

### vulnerabilities

- weaknesses in system that can be exploited
- e.g.
  - unpatched public-facing systems
  - software flaws
  - unsecured networks
  - human factors

### threats

- potential dangers that could cause harm to systems
- e.g.
  - malicious actor
  - malware
  - phishing email

### risk = vulnerability & threat & impact

- potential for loss/damage when threats exploit vulnerabilities

### owasp model

- risk = likelihood \* impact
- likelihood
  - threat agent factors
    - skill level
    - motive
    - opportunity
    - size
  - vulnerability factors
    - ease of discovery
    - ease of exploit
    - awareness
    - detection
- impact
  - technical impact factors
    - loss of confidentiality
    - loss of integrity
    - loss of availability
    - loss of accountability
  - business impact factors
    - financial damage
    - reputational damage
    - non-compliance
    - privacy violation

### fair model (factor analysis of info risk)

- quantitative risk analysis framework
- core concepts
  - loss event frequency (lef)
    - how often is a loss liekly to happen?
  - probable loss magnitude (plm)
    - how much will it cost when a loss event occurs?

### lef

- threat event frequency (tef) - how many times a threat agent is likely to attempt an attack over a given period
- vulnerability - probability that a threat event will cause a loss
  - function of threat capability (tcap) & resistance strength (rs)

### plm

- primary loss - direct financial costs that result from event itself
  - includes things like incident response effort, regulatory fines, cost to replace hardware
- secondary loss - ripple effect costs that appear after the event. often harder to quantify
  - includes reputational damage, customer churn, drop in stock price, competitive disadvantage

### estimate loss event frequency (lef)

- threat event frequency (tef)
  - how many times per year will a capable attacker attempt to use sql injection against a web app?
  - data gathering: we look at web app firewall (waf) logs, industry reports on attack frequency for our sector, threat intel feeds
  - estimate: based on data, estimate between 10-30 serious attempts per year
- vulnerability
  - when an attempt occurs, what is the probability that our controls will fail & a breach will happen?
  - data gathering: analyze strength of our controls. have an 80% effective waf & perform code reviews, but some legacy code is problematic. assess tcap vs rs
  - estimate controls will fail 5% & 15% of the time an attack occurs
- calculation
  - min lef: 10 attempts/year \* 5% failure rate = 0.5 times/year
  - max lef: 30 attempts/year \* 15% failure rate = 4.5 times/year
  - expect loss event to happen between 0.5-4.5 times/year

### estimate probable loss magnitude (plm)

- determine how much it will cost each time event happens. includes primary & secondary
- what are immediate, direct costs of breach?
- data gathering: estimate costs based on previous incidents or industry data
  - incident response: hiring forensics firm, overtime for internal staff ($50-100k)
  - regulatory fines: $10-20k
  - customer notification: $10-20k
- estimate: $80-170k

### secondary loss magnitude

- what are ripple effect costs?
- data gathering: harder to measure
  - reputation damage: estimated loss of future sales ($10-50k)
  - customer churn: $5-20k
- estimate: $15-70k

### plm

- min plm = $80k + $15k = $95k
- max plm = $170k + $70k = $240k
- costs between $95-240k

### calculate annualized risk (ale)

- combine frequency & magnitude estimates to get annualized risk in financial terms
- simple: min ale = 0.5 events/year _ $95k = $47.5k/year, max ale = 4.5 events/year _ $240k = $1.080m/year

### cyber kill chain

- recon
  - gather info about targets through osint, scanning, social engineering
- weaponization
  - malware payloads combined with exploits to create weaponized deliverables targeting specific vulnerabilities
- delivery
  - payload transmitted to targets via email, websites, other media
- exploitation
  - exploit code executes on target system, taking advantage of vulnerability to gain initial access. may involve triggering buffer overflows, executing malicious macros, or leveraging unpatched software flaws
- installation
  - attackers establish persistence by installing backdoors, remote access trojans (rats), or rootkits. ensure continued access even if initial vulnerability patched
- command & control (c2)
  - comm channels established between compromised systems & attacker controlled infrastructure, often using encrypted/covert channels to evade detection
- actions & objectives
  - lateral movement, data discovery, data exfiltration, evidence removal
