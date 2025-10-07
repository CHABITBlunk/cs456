# week 3

## passive recon

### open source intel (osint)

- intel derived from publicly available info
- encompasses vast array of data points, anything not classified or proprietary
- often starting point for understanding an org, individual, or system. provides context for later, more active phases
- e.g. news articles, social media, public records, company websites, technical forums, scientific papers
- data categories
  - technical data
    - domain & ip records
    - web technologies
    - code repos
  - org data
    - business registrations
    - news archives
    - physical locations
  - people data
    - employee profiles
    - social media
    - public dirs

### google dorking

- [cheat sheet](https://www.tutorialsfreak.com/ethical-hacking-tutorial/google-dorking-cheat-sheet)
- `site:` - limit to specific domain
- `inurl:`/`intitle:` - find strings in url/title
- `filetype:` - find specific file types
- `intext:` - find text in page body

### shodan

TODO: read up on shodan

### whois

- protocol that queries database to determine registered user/assignee of internet resource, such as domain name, ip block, autonomous system
- find contact info for domain owners, domain registration dates, expiration dates, dns servers, sometimes even registrar
- often first step in understanding who owns a particular website/ip
- info revealed
  - registrant name
  - registrant org
  - registrant contact info
  - admin contact
  - technical contact
  - registration date
  - expiration date
  - last updated date
  - name servers
  - registrar info

### other recon

- dns

  - https://dnsdumpster.com
  - cli: `dnsrecon -d <domain name> -n <dns server ip>`

- spiderfoot
  - both active & passive osint scanner
  - https://github.com/smicallef/spiderfoot
  - spiderfoot hx website

## active recon

### nessus

- extensive vulnerability db
- patch mgmt
- config auditing
- web app scanning
- compliance checks
- customizable policies
- detailed reporting

### openvas (open vulnerability assessment system)

- comprehensive vulnerability scanner that provides a free alternative to commercial solutions like nessus
- includes vulnerability database, scanning engine, & web based interface for mgmt & reporting
- use for regular vulnerability assessments, compliance auditing (for smaller orgs), internal security checks
- key features: full vulnerability scanning, compliance checks, reporting, scheduled scans, extensive plugins

### nmap

- one of most useful tools for active recon
- https://www.stationx.neet/nmap-cheat-sheet
- simple commands
  - figure what is up - `nmap -sn <target ip range>`
  - syn stealth scan (requires root) - `nmap -sS <target ip>`
  - tcp conn scan - `nmap -sT <target ip>`
  - udp scan (requires root) - `nmap -sU <target ip>`
  - ports - `nmap -p <port(s)> <target ip>`
    - specific ports - `80,443,22`
    - range of ports - `1-1024`
    - all ports - `-p-`
  - service/version detection - `nmap -sV <target ip>`
  - os detection (requires sudo) - `nmap -O <target ip>`
  - combined scans are alloewd
- nmap scripting engine (nse)
  - allows writing & sharing simple scripts to automate various networking tasks
  - can also perform
    - vulnerability detection
    - advanced service discovery
    - backdoor detection
    - brute force attacks
    - info gathering
  - categories: auth, vuln, discovery, dos, fuzzer, intrusive, safe, version
