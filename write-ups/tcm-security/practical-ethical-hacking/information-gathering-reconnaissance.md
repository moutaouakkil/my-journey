# Information Gathering (Reconnaissance)

## Passive Recon

**Physical Engagement/Social Engineering:**

* Location Information:
  * Satellite images
  * Drone recon
  * Building layout (badge readers, break areas, security, fencing)
* Job Information:
  * Employees (name, job title, phone number, manager, etc.)
  * Pictures (badge photos, desk photos, computer photos, etc.)



**Web/Host:**

* Target Validation: [WHOIS](https://who.is), [nslookup](https://www.nslookup.io), [dnsrecon](https://www.kali.org/tools/dnsrecon)
* Finding Subdomains: [Google FU](https://github.com/champmq/GoogleFU), [dig](https://toolbox.googleapps.com/apps/dig), [Nmap](https://nmap.org), [Sublist3r](https://www.kali.org/tools/sublist3r), [Bluto](https://github.com/darryllane/Bluto), [crt.sh](https://crt.sh), etc.
* Fingerpriting: [Nmap](https://nmap.org), [Wappalyzer](https://www.wappalyzer.com), [WhatWeb](https://whatweb.net), [BuiltWith](https://builtwith.com), [Netcat](https://sectools.org/tool/netcat)
* Data Breaches: [HaveIBeenPwned](https://haveibeenpwned.com), [Breach-Parse](https://github.com/hmaverickadams/breach-parse), [WeLeakInfo](https://weleakinfo.io)



## Identifying The Target

Use [Bugcrowd](https://bugcrowd.com) (a public Bug Bounty Program) to identify the target T-Mobile.

<figure><img src="../../../.gitbook/assets/image (35).png" alt="T-Mobile"><figcaption><p><a href="https://bugcrowd.com/engagements/t-mobile">https://bugcrowd.com/engagements/t-mobile</a></p></figcaption></figure>

Read the program details carefully and ensure that your testing activities comply with the authorized targets and rules outlined.



## Discovering Email Addresses

[Hunter.io](https://hunter.io): find and verify professional email addresses

<figure><img src="../../../.gitbook/assets/Untitled (2).png" alt="T-Mobile email addresses found using Hunter.io"><figcaption><p><a href="https://hunter.io/try/search/t-mobile.com?locale=en">https://hunter.io/try/search/t-mobile.com?locale=en</a></p></figcaption></figure>



[Phonebook.cz](https://phonebook.cz): lists all domains, email addresses, or URLs for the given input domain.

[Voila Norbert](https://www.voilanorbert.com): great for getting the email addresses you need.

[Clearbit](https://clearbit.com): free, verified B2B emails (it has to be used on Chrome).

[Email Hippo](https://tools.emailhippo.com): free online email verification tool.



## Gathering Breached Credentials with Breach-Parse

[breach-parse](https://github.com/hmaverickadams/breach-parse): A tool for parsing breached passwords

```sh
breach-parse @t-mobile.com t-mobile.txt "~/Downloads/BreachCompilation/data"
```

The obtained results can be leveraged for Credential Stuffing and Password Spraying.



## Hunting Breached Credentials with DeHashed

[DeHashed](https://dehashed.com): Have you been compromised? DeHashed provides free deep-web scans and protection against credential leaks.

<figure><img src="../../../.gitbook/assets/image (38).png" alt=""><figcaption><p><a href="https://dehashed.com/">https://dehashed.com</a></p></figcaption></figure>

Hashes.org is down, therefore, use [Hashes.com](https://hashes.com/en/decrypt/hash) or other tools to decrypt the hashed passwords.
