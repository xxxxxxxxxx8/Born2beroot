# Born2beRoot Student Guide

> A structured 1337/42 reference for building, securing, administering, monitoring, and defending a Debian virtual machine.

![42 Born2beRoot](https://img.shields.io/badge/42-Born2beRoot-000000?style=flat-square&logo=42)
![Debian](https://img.shields.io/badge/OS-Debian-A81D33?style=flat-square&logo=debian&logoColor=white)
![VirtualBox](https://img.shields.io/badge/Virtualization-VirtualBox-183A61?style=flat-square&logo=virtualbox&logoColor=white)
![Bash](https://img.shields.io/badge/Automation-Bash-4EAA25?style=flat-square&logo=gnu-bash&logoColor=white)

## Table of Contents

- [Purpose and Learning Outcomes](#purpose-and-learning-outcomes)
- [Important Safety Rules](#important-safety-rules)
- [Prerequisites and Placeholders](#prerequisites-and-placeholders)
- [Part 1 - Download and Prepare the Virtual Machine](#part-1---download-and-prepare-the-virtual-machine)
- [Part 2 - Create the VirtualBox Machine](#part-2---create-the-virtualbox-machine)
- [Part 3 - Install Debian](#part-3---install-debian)
- [Part 4 - Configure the Server](#part-4---configure-the-server)
- [Part 5 - Connect Through SSH](#part-5---connect-through-ssh)
- [Part 6 - Apply Security and Automation](#part-6---apply-security-and-automation)
- [Part 7 - Generate `signature.txt`](#part-7---generate-signaturetxt)
- [Part 8 - Defence Evaluation Questions](#part-8---defence-evaluation-questions)
- [Final Verification](#final-verification)
- [References](#references)

## Purpose and Learning Outcomes

Born2beRoot is a system-administration project. Its purpose is to make the student design and operate a small Linux server rather than simply install an operating system. The final machine should have a controlled administrative model, encrypted storage, restricted network access, a strong password policy, an auditable `sudo` configuration, a monitoring script, and scheduled automation.

This guide uses Debian because it is recommended for newcomers in the project subject and provides a large ecosystem of documentation and packages. The final implementation must always match the current subject and the requirements of the evaluator.

The project connects the following concepts:

| Concept | Practical implementation |
|---|---|
| Virtualization | Debian runs as a guest system inside VirtualBox. |
| Identity | The machine has a hostname, a root account, and a normal user account. |
| Privilege management | Administrative commands are executed through `sudo`. |
| Storage security | The virtual disk uses encrypted storage and LVM. |
| Network security | SSH is moved to port `4242` and protected by UFW. |
| Authentication policy | PAM and `/etc/login.defs` enforce password quality and aging. |
| Observability | `monitoring.sh` reports important server metrics. |
| Automation | `cron` executes the monitoring script every ten minutes. |
| Defence preparation | The student can explain the purpose of every configuration choice. |

## Important Safety Rules

The commands in this guide modify authentication, storage, network access, and privilege configuration. Run them only inside the intended virtual machine. Confirm the target disk before partitioning, and create a VirtualBox snapshot before editing PAM, SSH, or `sudo` configuration.

Never reuse the same password for every account. Use a unique password for the root account, the normal user, and the encryption passphrase. Do not publish credentials, private keys, database passwords, personal IP addresses, or terminal history in a public repository.

The project subject is the final authority. This document is a learning aid and may contain examples that must be adapted to the Debian release, VirtualBox version, keyboard layout, and exact rules used for your evaluation.

## Prerequisites and Placeholders

Install [Oracle VirtualBox](https://www.virtualbox.org/wiki/Downloads) and download the Debian installer from the [official Debian download page](https://www.debian.org/download). On 42 school computers, store large virtual-machine files in the location recommended by your campus, such as `sgoinfre`, when that storage is available.

The guide uses these placeholders:

| Placeholder | Meaning |
|---|---|
| `<login>` | Your 42 Intra username. |
| `<hostname>` | The hostname required by the subject, often `<login>42`. |
| `<password>` | A secret chosen by you; never copy a password from this guide. |
| `<vm-directory>` | The directory containing the VirtualBox machine files. |
| `<disk-file>` | The final `.vdi` file used to generate the signature. |

# Part 1 - Download and Prepare the Virtual Machine

## 1. Download the Debian ISO

Use the official Debian download page or the current Debian network-install directory. Select the installer image allowed by the subject. A network installer is small and downloads packages during installation, so an active network connection is required.

```text
https://www.debian.org/download
```

Verify that the file has an `amd64` architecture when the host and project requirements use a 64-bit Intel or AMD environment. Do not rename a file in a way that hides its actual format.

## 2. Optional 42 campus storage

This section applies only when the school environment provides a shared `sgoinfre` area. The exact path can differ between campuses.

```bash
cd /sgoinfre/students
mkdir <login>
chmod 700 <login>
```

Copy the Debian ISO into the directory created for your account. The permission `700` allows the owner to access the directory while preventing other users from browsing it.

Do not assume that shared storage is a backup. Keep an additional copy of important project files in an approved private location.

