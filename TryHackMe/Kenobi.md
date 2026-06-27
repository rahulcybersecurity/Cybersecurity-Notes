# Kenobi - TryHackMe

## Objective

The goal of this room was to practice network enumeration, identify exposed services, discover misconfigurations, and perform Linux privilege escalation through a realistic attack chain.

---

## Skills Practiced

* Nmap Scanning
* Service Enumeration
* SMB Enumeration
* NFS Enumeration
* File Discovery
* Linux Privilege Escalation
* Attack Path Identification

---

## Tools Used

* Nmap
* smbclient
* nmap NSE scripts
* NFS utilities
* Linux command line tools

---

## Enumeration

### Initial Reconnaissance

Started by performing network reconnaissance to identify open ports and running services.

Example commands:

```bash
nmap -sC -sV <target-ip>
```

Key findings:

* Multiple network services were exposed.
* Service versions provided useful information for further investigation.
* Enumeration revealed potential attack surfaces.

### SMB Enumeration

Investigated SMB shares to identify accessible files and directories.

Example commands:

```bash
smbclient -L //<target-ip>/
```

Learning points:

* SMB shares may contain sensitive information.
* Publicly accessible shares can reveal credentials, configuration files, or internal data.

### NFS Enumeration

Examined NFS exports to identify misconfigured network shares.

Example commands:

```bash
showmount -e <target-ip>
```

Learning points:

* NFS misconfigurations can expose critical files.
* Network shares should be reviewed carefully during enumeration.

---

## Privilege Escalation

During this room, privilege escalation was achieved by identifying a misconfiguration and leveraging it to gain elevated access.

Key concepts learned:

* Always inspect service configurations.
* Misconfigured binaries can become escalation vectors.
* Small pieces of information gathered during enumeration can become critical later.

Common Linux enumeration commands:

```bash
whoami
id
sudo -l
find / -perm -4000 2>/dev/null
```

---

## Key Learning Points

* Enumeration is often more important than exploitation.
* Every open service should be investigated.
* SMB and NFS services can expose valuable information.
* Multiple low-risk findings can be chained together.
* Privilege escalation opportunities frequently originate from earlier enumeration results.

---

## My Experience

This room significantly improved my understanding of how attackers move from information gathering to privilege escalation.

The biggest lesson I learned was that successful exploitation often depends on thorough enumeration rather than advanced exploits.

I also gained practical experience working with SMB, NFS, and Linux privilege escalation techniques in a realistic environment.

---

## What I Learned

* How to perform structured enumeration.
* How SMB and NFS services can expose sensitive information.
* The importance of documenting findings during assessments.
* How misconfigurations can lead to privilege escalation.
* Why enumeration is the foundation of penetration testing.
