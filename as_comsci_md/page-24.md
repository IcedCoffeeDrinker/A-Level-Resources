# 6.2 Security

## Threats to system and data security:
- human error (mistakes)
- internal problems/mismanagement
- natural disasters
- unauthorized intrusion
- installation of malware

hacker => someone that wants to gain unauthorized access to a system or data
malware => **malicious software** that wants to harm the system

## Types of Malware
- **Virus:** tries to replicate itself into other executable programms
    - ↳ boot sector virus: runs on boot
    - ↳ macro virus: hides in macros, usually Word, Excel, PowerPoint
- **worm:** runs independently and spreads to other hosts (computers)
    - ↳ a spreading virus
- **logic bomb:** stays inactive until some condition is met
- **Trojan horse:** replaces all or part of an initially useful program
- **Spyware:** collects information and sends it to another system
- **bot:** uses the infected computer to launch attacks

## Introduction of Malware:
- **Phishing:** sending a digital message from a seemingly authentic source that asks for confidential information
- **Pharming:** A mock up website that asks for your credentials while impersonating a different website
- **keylogger:** records all keys pressed by the user

## Sources of Vulnerability
### User:
- creates weak passwords
- might fall for phishing or pharming attacks
- introduce malware:
    - attaching e.g. a foreign USB
    - opening an email attatchment
    - accessing malicious websites
    - download malicious files

### System:
- The OS usually is very vulnerable.
    - More complex OS -> more weak spots
- Viruses hidden in default macros/dependencies of software
    - ↳ will always be installed
- buffer overflow can be used to gain unauthorized access
    - ↳ hacker overides permission files

## Security Measures
### Disaster recovery
=> restart programs fast to prevent other dependent programs from breaking down
- Disaster Recovery Contingency Plan
    - provides a packup system at any times
    - ↳ packup system is called 'hot site'
    - ↳ has to be remote from original system (bc. e.g. earthquake)

### Parallel System Update
- used to run a system continuously, e.g. web-services
- has two systems in parallel:
    - one updating
    - one providing the service

### User Authentication
- Even single-user systems should have user-accounts
    - ↳ restricts easy done damage
- Users have to authenticate themselves with (usually) an ASCII password
- a good password is long and complex
- Alternative authentication methods:
    - biometric auth. (e.g. Face ID or fingerprint)
    - security tokens: physical hardware for identification (e.g. NFC)

### Good Practice
- turn of computer when it's not in use
- enter the password in secret
- keep the password only in your mind
- organizations banning the use of portable storage devices

### Firewall
- primary defence against malware
- => a hardware device that inspects and controlls all traffic
    - ↳ sometimes it's a software
- checks system addresses and IPs
- (sometimes) checks for malicious data
- can include filters (e.g. for inappropriate websites)

### Digital Signature
- a way of verifying a computer's identity (e.g. sometimes sent along emails)

### Anti-Virus Software
=> software that regularly scanns the system for malware/viruses and deletes them

### Intrusion Detection
- monitors physical inputs and checks for differences in performed actions
    - ↳ recognizes when someone remotely takes controll or programs that act as users

### Arms Race
- Hacking software and anti-malware software become increasingly sophisticated
- It's a constant race of trying to supass eachother

## Security Measures for Data Protection
### Data Loss
- reasons for data loss:
    - storage device gets corrupted/destroyed
    - system crashes
    - faulty deletion/overwriting of files
    - file location forgotten
- A good backup procedure:
    - full backups made regularly (e.g. weekly)
    - two or more full backups kept in storage
    - daily incremental backups
    - backups stored outside of the system
        - ↳ fire-and flood proof location
- Ways of copying continuously changing data:
    - freeze file store while copying -> temporarily use memory as storage
    - use of disk-mirroring: files are always stored on two identical disks during normal operation
        - ↳ one disk is remote

### Restricting Access to Data
- user categories that restrict information available (e.g. employee vs. employer vs. admin)
- **Authorization policies** grant access rights (e.g. read or write) to users

### Storage Encryption
- All data on a disk can be encrypted to give intruders a hard time

## Exam Style 2, 4a, b
### 2a)
**i**
1. Data is lost
2. There is no connection to the server
3. The user isn't authorized

**ii**
1. Turn of the computer when not using it
2. Don't plug unknown external storage devices into any computer
3. Keep your password secret

### b)
**i**
This could be a natural desaster, e.g. an earthquake or a hacker attack that compromised the main system

**ii**
A hot-site which is a backup system that takes the place of the main system if it gets compromised for some reason.
> _book has different interpretation_

### c)
1. Regular backups could be created every week and incremental backups every day.
2. All storage could be mirrored onto a remote storage device that is locked away in a flood-and fireproof location.

### 4a
A firewall inspects and controlls all traffic entering and leaving a network. It is able to block connections if required. -> _exist both as a device but also locally_
Authentication means that users have to prove that they are allowed to have access to a system or file. This can be through a password, biometric data, etc.

### 4b)
Data integrity includes the condition that the data has to be up-to-date while data security simply garuantees that data doesn't get lost.
Another difference is that data integrity requires data to be accurate while data security requires data not be corrupt or change unexpectedly.
> (In both cases Data Security is contained in data integrity, as it is a prerequisite for it.)