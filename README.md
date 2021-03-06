# Active Directory Kill Chain Attack & Defense

<img width="650" src="https://camo.githubusercontent.com/9547d8152e3490a6e5e3da0279faab64340885be/68747470733a2f2f646f63732e6d6963726f736f66742e636f6d2f656e2d75732f616476616e6365642d7468726561742d616e616c79746963732f6d656469612f61747461636b2d6b696c6c2d636861696e2d736d616c6c2e6a7067">

## Summary
This document was designed to be a useful, informational asset for those looking to understand the specific tactics, techniques, and procedures (TTPs) attackers are leveraging to compromise active directory and guidance to mitigation, detection, and prevention. And understand Active Directory Kill Chain Attack and Modern Post Exploitation Adversary Tradecraft Activity.

## Table of Contents
* [Discovery](#discovery)
* [Privilege Escalation](#privilege-escalation)
* [Defense Evasion](#defense-evasion)
* [Credential Dumping](#credential-dumping)
* [Lateral Movement](#lateral-movement)
* [Persistence](#persistence)
* [Defense & Detection](#defense-&-detection)

<hr>

## Discovery
### SPN Scanning
* [SPN Scanning – Service Discovery without Network Port Scanning](https://adsecurity.org/?p=1508)

### Data Mining
* [A Data Hunting Overview](https://thevivi.net/2018/05/23/a-data-hunting-overview/)
* [Push it, Push it Real Good](https://www.harmj0y.net/blog/redteaming/push-it-push-it-real-good/)

### User Hunting
* [Hidden Administrative Accounts: BloodHound to the Rescue](https://www.crowdstrike.com/blog/hidden-administrative-accounts-bloodhound-to-the-rescue/)
* [Active Directory Recon Without Admin Rights](https://adsecurity.org/?p=2535)
* [Gathering AD Data with the Active Directory PowerShell Module](https://adsecurity.org/?p=3719)
* [Using ActiveDirectory module for Domain Enumeration from PowerShell Constrained Language Mode](http://www.labofapenetrationtester.com/2018/10/domain-enumeration-from-PowerShell-CLM.html)
* [PowerUpSQL Active Directory Recon Functions](https://github.com/NetSPI/PowerUpSQL/wiki/Active-Directory-Recon-Functions)
* [Derivative Local Admin](https://www.sixdub.net/?p=591)
* [Dumping Active Directory Domain Info – with PowerUpSQL!](https://blog.netspi.com/dumping-active-directory-domain-info-with-powerupsql/)
* [Local Group Enumeration](https://www.harmj0y.net/blog/redteaming/local-group-enumeration/)
* [Attack Mapping With Bloodhound](https://blog.stealthbits.com/local-admin-mapping-bloodhound)

### LAPS
* [Microsoft LAPS Security & Active Directory LAPS Configuration Recon](https://adsecurity.org/?p=3164)
* [Running LAPS with PowerView](https://www.harmj0y.net/blog/powershell/running-laps-with-powerview/)
* [RastaMouse LAPS Part 1 & 2](https://rastamouse.me/tags/laps/)

<hr>

## Privilege Escalation
### Passwords in SYSVOL & Group Policy Preferences
* [Finding Passwords in SYSVOL & Exploiting Group Policy Preferences](https://adsecurity.org/?p=2288)
* [Pentesting in the Real World: Group Policy Pwnage](https://blog.rapid7.com/2016/07/27/pentesting-in-the-real-world-group-policy-pwnage/)

### MS14-068 Kerberos Vulnerability
* [MS14-068: Vulnerability in (Active Directory) Kerberos Could Allow Elevation of Privilege](https://adsecurity.org/?p=525)
* [Digging into MS14-068, Exploitation and Defence](https://labs.mwrinfosecurity.com/blog/digging-into-ms14-068-exploitation-and-defence/)
* [From MS14-068 to Full Compromise – Step by Step](https://www.trustedsec.com/2014/12/ms14-068-full-compromise-step-step/)

### DNSAdmins
* [Abusing DNSAdmins privilege for escalation in Active Directory](http://www.labofapenetrationtester.com/2017/05/abusing-dnsadmins-privilege-for-escalation-in-active-directory.html)
* [From DNSAdmins to Domain Admin, When DNSAdmins is More than Just DNS Administration](https://adsecurity.org/?p=4064)

### Unconstrained Delegation
* [Domain Controller Print Server + Unconstrained Kerberos Delegation = Pwned Active Directory Forest](https://adsecurity.org/?p=4056)
* [Active Directory Security Risk #101: Kerberos Unconstrained Delegation (or How Compromise of a Single Server Can Compromise the Domain)](https://adsecurity.org/?p=1667)
* [Unconstrained Delegation Permissions](https://blog.stealthbits.com/unconstrained-delegation-permissions/)
* [Trust? Years to earn, seconds to break](https://labs.mwrinfosecurity.com/blog/trust-years-to-earn-seconds-to-break/)

### Constrained Delegation
* [Another Word on Delegation](https://www.harmj0y.net/blog/redteaming/another-word-on-delegation/)
* [From Kekeo to Rubeus](https://www.harmj0y.net/blog/redteaming/from-kekeo-to-rubeus/)
* [S4U2Pwnage](http://www.harmj0y.net/blog/activedirectory/s4u2pwnage/)
* [Kerberos Delegation, Spns And More...](https://www.secureauth.com/blog/kerberos-delegation-spns-and-more)

### Insecure Group Policy Object Permission Rights
* [Abusing GPO Permissions](https://www.harmj0y.net/blog/redteaming/abusing-gpo-permissions/)
* [A Red Teamer’s Guide to GPOs and OUs](https://wald0.com/?p=179)

### Insecure ACLs Permission Rights
* [Exploiting Weak Active Directory Permissions With Powersploit](https://blog.stealthbits.com/exploiting-weak-active-directory-permissions-with-powersploit/)
* [Escalating privileges with ACLs in Active Directory
](https://blog.fox-it.com/2018/04/26/escalating-privileges-with-acls-in-active-directory/)
* [Abusing Active Directory Permissions with PowerView
](http://www.harmj0y.net/blog/redteaming/abusing-active-directory-permissions-with-powerview/)
* [BloodHound 1.3 – The ACL Attack Path Update](https://wald0.com/?p=112)
* [Scanning for Active Directory Privileges & Privileged Accounts](https://adsecurity.org/?p=3658)

### Domain Trusts
* [A Guide to Attacking Domain Trusts](http://www.harmj0y.net/blog/redteaming/a-guide-to-attacking-domain-trusts/)
* [It's All About Trust – Forging Kerberos Trust Tickets to Spoof Access across Active Directory Trusts](https://adsecurity.org/?p=1588)
* [Active Directory forest trusts part 1 - How does SID filtering work?](https://dirkjanm.io/active-directory-forest-trusts-part-one-how-does-sid-filtering-work)
* [The Forest Is Under Control. Taking over the entire Active Directory forest](https://hackmag.com/security/ad-forest/)

### DCShadow
* [Privilege Escalation With DCShadow](https://blog.stealthbits.com/privilege-escalation-with-dcshadow/)
* [DCShadow](https://pentestlab.blog/2018/04/16/dcshadow/)
* [DCShadow explained: A technical deep dive into the latest AD attack technique](https://blog.alsid.eu/dcshadow-explained-4510f52fc19d)
* [DCShadow - Minimal permissions, Active Directory Deception, Shadowception and more](http://www.labofapenetrationtester.com/2018/04/dcshadow.html)

### RID
* [Rid Hijacking: When Guests Become Admins](https://blog.stealthbits.com/rid-hijacking-when-guests-become-admins/)

### Microsoft SQL Server
* [How to get SQL Server Sysadmin Privileges as a Local Admin with PowerUpSQL](https://blog.netspi.com/get-sql-server-sysadmin-privileges-local-admin-powerupsql/)
* [Compromise With Powerupsql – Sql Attacks](https://blog.stealthbits.com/compromise-with-powerupsql-sql-attacks/)

### Red Forest
* [Attack and defend Microsoft Enhanced Security Administrative](https://download.ernw-insight.de/troopers/tr18/slides/TR18_AD_Attack-and-Defend-Microsoft-Enhanced-Security.pdf)

<hr>

## Lateral Movement
### Microsoft SQL Server Database links
* [SQL Server – Link… Link… Link… and Shell: How to Hack Database Links in SQL Server!](https://blog.netspi.com/how-to-hack-database-links-in-sql-server/)
* [SQL Server Link Crawling with PowerUpSQL](https://blog.netspi.com/sql-server-link-crawling-powerupsql/)

### Pass The Hash
* [Performing Pass-the-hash Attacks With Mimikatz](https://blog.stealthbits.com/passing-the-hash-with-mimikatz)
* [How to Pass-the-Hash with Mimikatz](https://blog.cobaltstrike.com/2015/05/21/how-to-pass-the-hash-with-mimikatz/)

### System Center Configuration Manager (SCCM)
* [Targeted Workstation Compromise With Sccm](https://enigma0x3.net/2015/10/27/targeted-workstation-compromise-with-sccm/)

### WSUS
* [Remote Weaponization of WSUS MITM](https://www.sixdub.net/?p=623)
* [WSUSpendu](https://www.blackhat.com/docs/us-17/wednesday/us-17-Coltel-WSUSpendu-Use-WSUS-To-Hang-Its-Clients-wp.pdf)

### Password Spraying
* [Password Spraying Windows Active Directory Accounts - Tradecraft Security Weekly #5](https://www.youtube.com/watch?v=xB26QhnL64c)
* [Attacking Exchange with MailSniper](https://www.blackhillsinfosec.com/attacking-exchange-with-mailsniper/)

<hr>

## Defense Evasion

### In-Memory Evasion
* [Bypassing Memory Scanners with Cobalt Strike and Gargoyle](https://labs.mwrinfosecurity.com/blog/experimenting-bypassing-memory-scanners-with-cobalt-strike-and-gargoyle/)
* [In-Memory Evasions Course](https://www.youtube.com/playlist?list=PL9HO6M_MU2nc5Q31qd2CwpZ8J4KFMhgnK)
* [Bring Your Own Land (BYOL) – A Novel Red Teaming Technique](https://www.fireeye.com/blog/threat-research/2018/06/bring-your-own-land-novel-red-teaming-technique.html)

### Endpoint Detection and Response (EDR) Evasion
* [Red Teaming in the EDR age](https://youtu.be/l8nkXCOYQC4)

### OPSEC
* [Modern Defenses and YOU!](https://blog.cobaltstrike.com/2017/10/25/modern-defenses-and-you/)
* [OPSEC Considerations for Beacon Commands](https://blog.cobaltstrike.com/2017/06/23/opsec-considerations-for-beacon-commands/)
* [Red Team Tradecraft and TTP Guidance](https://sec564.com/#!docs/tradecraft.md)
* [Fighting the Toolset](https://www.youtube.com/watch?v=RoqVunX_sqA)

### Microsoft ATA & ATP Evasion
* [Red Team Techniques for Evading, Bypassing, and Disabling MS
Advanced Threat Protection and Advanced Threat Analytics](https://www.blackhat.com/docs/eu-17/materials/eu-17-Thompson-Red-Team-Techniques-For-Evading-Bypassing-And-Disabling-MS-Advanced-Threat-Protection-And-Advanced-Threat-Analytics.pdf)
* [Red Team Revenge - Attacking Microsoft ATA](https://www.slideshare.net/nikhil_mittal/red-team-revenge-attacking-microsoft-ata)
* [Evading Microsoft ATA for Active Directory Domination](https://www.slideshare.net/nikhil_mittal/evading-microsoft-ata-for-active-directory-domination)

### PowerShell ScriptBlock Logging Bypass
* [PowerShell ScriptBlock Logging Bypass](https://cobbr.io/ScriptBlock-Logging-Bypass.html)

### PowerShell Anti-Malware Scan Interface (AMSI) Bypass
* [How to bypass AMSI and execute ANY malicious Powershell code](https://0x00-0x00.github.io/research/2018/10/28/How-to-bypass-AMSI-and-Execute-ANY-malicious-powershell-code.html)
* [AMSI: How Windows 10 Plans to Stop Script-Based Attacks](https://www.blackhat.com/docs/us-16/materials/us-16-Mittal-AMSI-How-Windows-10-Plans-To-Stop-Script-Based-Attacks-And-How-Well-It-Does-It.pdf)
* [AMSI Bypass: Patching Technique](https://www.cyberark.com/threat-research-blog/amsi-bypass-patching-technique/)

### AppLocker & Device Guard Bypass
* [Living Off The Land Binaries And Scripts - (LOLBins and LOLScripts)](https://github.com/LOLBAS-Project/LOLBAS)

### Sysmon Evasion
* [Subverting Sysmon: Application of a Formalized Security Product Evasion Methodology](https://github.com/mattifestation/BHUSA2018_Sysmon)

### HoneyTokens Evasion
* [Forging Trusts for Deception in Active Directory](http://www.labofapenetrationtester.com/2018/10/deploy-deception.html)
* [Honeypot Buster: A Unique Red-Team Tool](https://jblog.javelin-networks.com/blog/the-honeypot-buster/)

<hr>

## Credential Dumping
### NTDS.DIT Password Extraction
* [How Attackers Pull the Active Directory Database (NTDS.dit) from a Domain Controller](https://adsecurity.org/?p=451)
* [Extracting Password Hashes From The Ntds.dit File](https://blog.stealthbits.com/extracting-password-hashes-from-the-ntds-dit-file/)

### Kerberoasting
* [Kerberoasting Without Mimikatz](https://www.harmj0y.net/blog/powershell/kerberoasting-without-mimikatz/)
* [Cracking Kerberos TGS Tickets Using Kerberoast – Exploiting Kerberos to Compromise the Active Directory Domain](https://adsecurity.org/?p=2293)
* [Extracting Service Account Passwords With Kerberoasting](https://blog.stealthbits.com/extracting-service-account-passwords-with-kerberoasting/)
* [Cracking Service Account Passwords with Kerberoasting](https://www.cyberark.com/blog/cracking-service-account-passwords-kerberoasting/)

### Kerberos AP-REP Roasting
* [Roasting AS-REPs](http://www.harmj0y.net/blog/activedirectory/roasting-as-reps/) 

### Windows Credential Manager/Vault
* [Operational Guidance for Offensive User DPAPI Abuse](https://www.harmj0y.net/blog/redteaming/operational-guidance-for-offensive-user-dpapi-abuse/)

### DCSync
* [Mimikatz and DCSync and ExtraSids, Oh My](https://www.harmj0y.net/blog/redteaming/mimikatz-and-dcsync-and-extrasids-oh-my/)
* [Mimikatz DCSync Usage, Exploitation, and Detection](https://adsecurity.org/?p=1729)

### LLMNR/NBT-NS Poisoning
* [LLMNR/NBT-NS Poisoning Using Responder](https://www.4armed.com/blog/llmnr-nbtns-poisoning-using-responder/)

<hr>

## Persistence
### Golden Ticket
* [Golden Ticket](https://pentestlab.blog/2018/04/09/golden-ticket/)
* [Kerberos Golden Tickets are Now More Golden](https://adsecurity.org/?p=1640)

### SID History
* [Sneaky Active Directory Persistence #14: SID History](https://adsecurity.org/?p=1772)

### Silver Ticket
* [How Attackers Use Kerberos Silver Tickets to Exploit Systems](https://adsecurity.org/?p=2011)
* [Sneaky Active Directory Persistence #16: Computer Accounts & Domain Controller Silver Tickets](https://adsecurity.org/?p=2753)

### DCShadow
* [Creating Persistence With Dcshadow](https://blog.stealthbits.com/creating-persistence-with-dcshadow/)

### AdminSDHolder
* [Sneaky Active Directory Persistence #15: Leverage AdminSDHolder & SDProp to (Re)Gain Domain Admin Rights](https://adsecurity.org/?p=1906)
* [Persistence Using Adminsdholder And Sdprop](https://blog.stealthbits.com/persistence-using-adminsdholder-and-sdprop/)

### Group Policy Object
* [Sneaky Active Directory Persistence #17: Group Policy](https://adsecurity.org/?p=2716)

### Skeleton Keys
* [Unlocking All The Doors To Active Directory With The Skeleton Key Attack](https://blog.stealthbits.com/unlocking-all-the-doors-to-active-directory-with-the-skeleton-key-attack/)
* [Skeleton Key](https://pentestlab.blog/2018/04/10/skeleton-key/)
* [Attackers Can Now Use Mimikatz to Implant Skeleton Key on Domain Controllers & BackDoor Your Active Directory Forest](https://adsecurity.org/?p=1275)

### SeEnableDelegationPrivilege
* [The Most Dangerous User Right You (Probably) Have Never Heard Of](https://www.harmj0y.net/blog/activedirectory/the-most-dangerous-user-right-you-probably-have-never-heard-of/)
* [SeEnableDelegationPrivilege Active Directory Backdoor](https://www.youtube.com/watch?v=OiqaO9RHskU)

### Security Support Provider
* [Sneaky Active Directory Persistence #12: Malicious Security Support Provider (SSP)](https://adsecurity.org/?p=1760)

### Directory Services Restore Mode
* [Sneaky Active Directory Persistence #11: Directory Service Restore Mode (DSRM)](https://adsecurity.org/?p=1714)
* [Sneaky Active Directory Persistence #13: DSRM Persistence v2](https://adsecurity.org/?p=1785)

### ACLs & Security Descriptors
* [An ACE Up the Sleeve: Designing Active Directory DACL Backdoors](https://www.blackhat.com/docs/us-17/wednesday/us-17-Robbins-An-ACE-Up-The-Sleeve-Designing-Active-Directory-DACL-Backdoors-wp.pdf)
* [Shadow Admins – The Stealthy Accounts That You Should Fear The Most](https://www.cyberark.com/threat-research-blog/shadow-admins-stealthy-accounts-fear/)

### Tools & Scripts
* [PowerView](https://github.com/PowerShellMafia/PowerSploit/blob/master/Recon/PowerView.ps1) - Situational Awareness PowerShell framework
* [BloodHound](https://github.com/BloodHoundAD/BloodHound) - Six Degrees of Domain Admin
* [ADACLScanner](https://github.com/canix1/ADACLScanner) - A tool with GUI or command linte used to create reports of access control lists (DACLs) and system access control lists (SACLs) in Active Directory
* [PowerUpSQL](https://github.com/NetSPI/PowerUpSQL) - A PowerShell Toolkit for Attacking SQL Server
* [Rubeus](https://github.com/GhostPack/Rubeus) -  Rubeus is a C# toolset for raw Kerberos interaction and abuses
* [Mimikatz](https://github.com/gentilkiwi/mimikatz) - Utility to extract plaintexts passwords, hash, PIN code and kerberos tickets from memory but also perform pass-the-hash, pass-the-ticket or build Golden tickets
* [Grouper](https://github.com/l0ss/Grouper) - A PowerShell script for helping to find vulnerable settings in AD Group Policy.
* [Tools Cheat Sheets](https://github.com/HarmJ0y/CheatSheets) - Tools (PowerView, PowerUp, Empire, and PowerSploit)
<hr>

## Detect & Defense
### Tools & Scripts
* [SAMRi10 - Hardening SAM Remote Access in Windows 10/Server 2016](https://gallery.technet.microsoft.com/SAMRi10-Hardening-Remote-48d94b5b)
* [Net Cease - Hardening Net Session Enumeration](https://gallery.technet.microsoft.com/Net-Cease-Blocking-Net-1e8dcb5b)
* [PingCastle Active Directory Security Audit](https://www.pingcastle.com/)
* [Aorato Skeleton Key Malware Remote DC Scanner](https://gallery.technet.microsoft.com/Aorato-Skeleton-Key-24e46b73)
* [Reset the krbtgt account password/keys](https://gallery.technet.microsoft.com/Reset-the-krbtgt-account-581a9e51)
* [Deploy-Deception - A PowerShell module to deploy active directory decoy objects](https://github.com/samratashok/Deploy-Deception)
* [dcept - A tool for deploying and detecting use of Active Directory honeytokens](https://github.com/secureworks/dcept)
* [LogonTracer - Investigate malicious Windows logon by visualizing and analyzing Windows event log](https://github.com/JPCERTCC/LogonTracer)

### Detection
|Attack|Event ID|
|------|--------|
|Account and Group Enumeration|4798: A user's local group membership was enumerated<br>4799: A security-enabled local group membership was enumerated|
|AdminSDHolder|4780: The ACL was set on accounts which are members of administrators groups|
|Kekeo|4624: Account Logon<br>4672: Admin Logon<br>4768: Kerberos TGS Request|
|Silver	Ticket|4624: Account Logon<br>4634: Account Logoff<br>4672: Admin Logon|
|Golden	Ticket|4624: Account Logon<br>4672: Admin Logon|
|PowerShell|4103: Script Block Logging<br>400: Engine Lifecycle<br>403: Engine Lifecycle<br>4103: Module Logging<br>600: Provider Lifecycle<br>|
|DCShadow|4742: A computer account was changed<br>5137: A directory service object was created<br>5141: A directory service object was deleted<br>4929: An Active Directory replica source naming context was removed|
|Skeleton Keys|4673: A privileged service was called<br>4611: A trusted logon process has been registered with the Local Security Authority<br>4688: A new process has been created<br>4689: A new process has exited|
|PYKEK MS14-068|4672: Admin Logon<br>4624: Account Logon<br>4768: Kerberos TGS Request|
|Kerberoasting|4769: A Kerberos ticket was requested|
|Lateral Movement|4688: A new process has been created<br>4689: A process has exited<br>4624: An account was successfully logged on<br>4625: An account failed to log on|
|DCSync|4662: An operation was performed on an object|

### Resources
* [Reducing the Active Directory Attack Surface](https://docs.microsoft.com/en-us/windows-server/identity/ad-ds/plan/security-best-practices/reducing-the-active-directory-attack-surface)
* [Securing Domain Controllers to Improve Active Directory Security](https://adsecurity.org/?p=3377)
* [Securing Windows Workstations: Developing a Secure Baseline](https://adsecurity.org/?p=3299)
* [Implementing Secure Administrative Hosts](https://docs.microsoft.com/en-us/windows-server/identity/ad-ds/plan/security-best-practices/implementing-secure-administrative-hosts)
* [Privileged Access Management for Active Directory Domain Services](https://docs.microsoft.com/en-us/microsoft-identity-manager/pam/privileged-identity-management-for-active-directory-domain-services)
* [Awesome Windows Domain Hardening](https://github.com/PaulSec/awesome-windows-domain-hardening)
* [Best Practices for Securing Active Directory](https://docs.microsoft.com/en-us/windows-server/identity/ad-ds/plan/security-best-practices/best-practices-for-securing-active-directory)
* [Introducing the Adversary Resilience Methodology — Part One](https://posts.specterops.io/introducing-the-adversary-resilience-methodology-part-one-e38e06ffd604)
* [Introducing the Adversary Resilience Methodology — Part Two](https://posts.specterops.io/introducing-the-adversary-resilience-methodology-part-two-279a1ed7863d)
* [Mitigating Pass-the-Hash and Other Credential Theft, version 2](https://download.microsoft.com/download/7/7/A/77ABC5BD-8320-41AF-863C-6ECFB10CB4B9/Mitigating-Pass-the-Hash-Attacks-and-Other-Credential-Theft-Version-2.pdf)
* [Configuration guidance for implementing the Windows 10 and Windows Server 2016 DoD Secure Host Baseline settings](https://github.com/nsacyber/Windows-Secure-Host-Baseline)
* [Monitoring Active Directory for Signs of Compromise](https://docs.microsoft.com/en-us/windows-server/identity/ad-ds/plan/security-best-practices/monitoring-active-directory-for-signs-of-compromise)
* [Detecting Lateral Movement through Tracking Event Logs](https://www.jpcert.or.jp/english/pub/sr/Detecting%20Lateral%20Movement%20through%20Tracking%20Event%20Logs_version2.pdf)
* [Kerberos Golden Ticket Protection Mitigating Pass-the-Ticket on Active Directory](https://cert.europa.eu/static/WhitePapers/UPDATED%20-%20CERT-EU_Security_Whitepaper_2014-007_Kerberos_Golden_Ticket_Protection_v1_4.pdf)
* [Overview of Microsoft's "Best Practices for Securing Active Directory"](https://digital-forensics.sans.org/blog/2013/06/20/overview-of-microsofts-best-practices-for-securing-active-directory)
* [The Keys to the Kingdom: Limiting Active Directory Administrators](https://dsimg.ubm-us.net/envelope/155422/314202/1330537912_Keys_to_the_Kingdom_Limiting_AD_Admins.pdf)
* [The Most Common Active Directory Security Issues and What You Can Do to Fix Them](https://adsecurity.org/?p=1684)
* [Event Forwarding Guidance](https://github.com/nsacyber/Event-Forwarding-Guidance)
* [Planting the Red Forest: Improving AD on the Road to ESAE](https://www.mwrinfosecurity.com/our-thinking/planting-the-red-forest-improving-ad-on-the-road-to-esae/)
* [Detecting Kerberoasting Activity](https://adsecurity.org/?p=3458)
* [Security Considerations for Trusts](https://docs.microsoft.com/pt-pt/previous-versions/windows/server/cc755321(v=ws.10))
* [Advanced Threat Analytics suspicious activity guide](https://docs.microsoft.com/en-us/advanced-threat-analytics/suspicious-activity-guide)
* [Windows 10 Credential Theft Mitigation Guide](https://download.microsoft.com/download/C/1/4/C14579CA-E564-4743-8B51-61C0882662AC/Windows%2010%20credential%20theft%20mitigation%20guide.docx)
* [Detecting Pass-The- Ticket and Pass-The- Hash Attack Using Simple WMI Commands](https://blog.javelin-networks.com/detecting-pass-the-ticket-and-pass-the-hash-attack-using-simple-wmi-commands-2c46102b76bc)
* [Step by Step Deploy Microsoft Local Administrator Password Solution](https://gallery.technet.microsoft.com/Step-by-Step-Deploy-Local-7c9ef772)
* [Active Directory Security Best Practices](https://www.troopers.de/downloads/troopers17/TR17_AD_signed.pdf)
* [Finally Deploy and Audit LAPS with Project VAST, Part 1 of 2](https://blogs.technet.microsoft.com/jonsh/2018/10/03/finally-deploy-and-audit-laps-with-project-vast-part-1-of-2/)
* [Windows Security Log Events](https://www.ultimatewindowssecurity.com/securitylog/encyclopedia/default.aspx)
* [Talk Transcript BSidesCharm Detecting the Elusive: Active Directory Threat Hunting](https://www.trimarcsecurity.com/single-post/Detecting-the-Elusive-Active-Directory-Threat-Hunting)
* [Preventing Mimikatz Attacks](https://medium.com/blue-team/preventing-mimikatz-attacks-ed283e7ebdd5)
* [Understanding "Red Forest" - The 3-Tier ESAE and Alternative Ways to Protect Privileged Credentials](https://www.slideshare.net/QuestSoftware/understanding-red-forest-the-3tier-esae-and-alternative-ways-to-protect-privileged-credentials)
* [Monitors for DCSYNC and DCSHADOW attacks and create custom Windows Events for these events](https://github.com/shellster/DCSYNCMonitor)
* [Ten Process Injection Techniques: A Technical Survey Of Common And Trending Process Injection Techniques](https://www.endgame.com/blog/technical-blog/ten-process-injection-techniques-technical-survey-common-and-trending-process)
* [Hunting For In-Memory .NET Attacks](https://www.endgame.com/blog/technical-blog/hunting-memory-net-attacks)
* [Mimikatz Overview, Defenses and Detection](https://www.sans.org/reading-room/whitepapers/detection/mimikatz-overview-defenses-detection-36780)
* [Hunting for Gargoyle Memory Scanning Evasion](https://www.countercept.com/blog/hunting-for-gargoyle/)
* [Planning and getting started on the Windows Defender Application Control deployment process](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-deployment-guide)
* [How to Go from Responding to Hunting with Sysinternals Sysmon](https://onedrive.live.com/view.aspx?resid=D026B4699190F1E6!2843&ithint=file%2cpptx&app=PowerPoint&authkey=!AMvCRTKB_V1J5ow)

## License
[![CC0](http://mirrors.creativecommons.org/presskit/buttons/88x31/svg/cc-zero.svg)](http://creativecommons.org/publicdomain/zero/1.0)

To the extent possible under law, Rahmat Nurfauzi &#34;@infosecn1nja&#34; has waived all copyright and related or neighboring rights to this work.
