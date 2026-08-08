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

## 3. Install VirtualBox

On a personal computer, install VirtualBox from the official website. On a 42 Apple computer, use the Managed Software Center if that is the approved installation method.

# Part 2 - Create the VirtualBox Machine

## 1. Create the machine

Open VirtualBox and select **New**. Use a descriptive name such as `Born2beRoot-Debian`. Select Linux and Debian as the operating-system family and version when the interface offers those options.

![Create a new virtual machine](https://user-images.githubusercontent.com/58959408/174700376-2862e8e9-0a7a-4681-af3b-e82dbc7d9aa5.png)

## 2. Choose the storage location

On 42 school computers, store the machine in your permitted student directory, for example:

```text
<vm-directory>/<login>/Born2beRoot-Debian
```

Avoid storing a large virtual disk in a temporary or automatically cleaned directory.

![Select the machine folder](https://user-images.githubusercontent.com/58959408/174700651-8dc8e9a0-7709-4202-8a12-12a384ff6e3e.png)

## 3. Allocate memory and create the disk

Allocate memory that leaves enough resources for the host operating system. The original guide uses `1024 MB`; this may be sufficient for a minimal server, but the host and subject requirements take priority.

Create a virtual hard disk using the following choices:

| Setting | Recommended choice |
|---|---|
| Disk type | `VDI (VirtualBox Disk Image)` |
| Allocation | Dynamically allocated |
| Capacity | Use the size required by the subject; the original guide uses `12 GB`. |

Dynamic allocation allows the virtual-disk file to grow as data is written instead of reserving the full capacity immediately.

![Choose VDI](https://user-images.githubusercontent.com/58959408/174701340-d84f6c80-e09b-43ae-b31a-6dd5d6306f23.png)

![Choose dynamically allocated storage](https://user-images.githubusercontent.com/58959408/174744677-eac5b679-49f7-4881-a59b-00a420cbe640.png)

![Set the virtual-disk size](https://user-images.githubusercontent.com/58959408/174745855-7388098be69-45cc-bb6d-7c6c1a40c1ac.png)

## 4. Attach the Debian ISO

Open the virtual machine settings and select **Storage**. Select the empty optical drive, choose **Choose a disk file**, and attach the Debian ISO.

![Open VirtualBox storage settings](https://user-images.githubusercontent.com/58959408/175455682-e1b4c977-2f33-41cf-b3cc-3ad78b3254ce.png)

![Choose the ISO file](https://user-images.githubusercontent.com/58959408/174702002-9b4fe4d2-3008-4375-9ec1-57f5e1425eb8.png)

Start the virtual machine. The Debian installer is controlled mainly with the keyboard, so use the arrow keys, `Tab`, `Space`, and `Enter` to navigate.

# Part 3 - Install Debian

## 1. Language, country, and keyboard

Select the language and country appropriate for your environment. Choose the keyboard layout that matches the physical keyboard. A wrong layout can make symbols in passwords and commands difficult to type correctly.

![Debian installation menu](https://user-images.githubusercontent.com/58959408/174728861-fb9435a5-04e5-402c-80a3-f366c9b51be8.png)

## 2. Set the hostname and accounts

Set the hostname required by the subject. A common pattern is `<login>42`.

```text
Hostname: <hostname>
Domain name: leave empty unless required
```

Create a root password and a separate normal-user account. Use the normal account for daily work and reserve root privileges for controlled administrative operations.

> **Credential rule:** Write down the account roles, not the passwords in this README. A secure project should use separate, unique credentials rather than reusing one password everywhere.

## 3. Configure encrypted LVM

Choose the partitioning option required by the subject. A common guided choice is **Guided - use entire disk and set up encrypted LVM**, followed by the option that separates directories such as `/home`, `/var`, and `/tmp`.

The storage design has two layers:

1. **Encryption** protects data at rest inside the virtual disk.
2. **LVM** creates a storage pool from which logical volumes can be allocated and mounted separately.

Select the correct virtual disk, confirm the partition layout, and create a strong encryption passphrase. When the installer asks how much of the volume group should be used, choose the value required by the subject; the original guide uses the maximum available space.

![Choose encrypted LVM](https://user-images.githubusercontent.com/58959408/174730389-03e5dcd7-9472-4cab-bf88-fe3cc4dc0f4c.png)

![Select the disk](https://user-images.githubusercontent.com/58959408/174730452-e267df43-2883-4760-85c4-010970fee329.png)

![Separate mount points](https://user-images.githubusercontent.com/58959408/174730481-2641b9c0-c50d-4f2b-9e71-3896a0760e10.png)

When asked to erase data, the virtual disk is empty, so continue only after verifying that the selected disk belongs to the VM. Set and confirm the encryption passphrase.

![Set the encryption passphrase](https://user-images.githubusercontent.com/58959408/174730733-f306e051-4b0e-40de-93ab-56f2cdce45d5.png)

## 4. Select packages and install GRUB

Install only the software requested by the subject. For a minimal server, do not install a desktop environment. If the project requires SSH to be installed manually later, it is acceptable to deselect the SSH server during installation and configure it after the first boot.

Install GRUB on the virtual disk, normally `/dev/sda` in a simple VirtualBox configuration. The device name may differ, so verify it before confirming.

![Select Debian software](https://user-images.githubusercontent.com/58959408/174731387-b4859ded-9a9f-409a-a9c9-57d1ec77cbfd.png)

![Install GRUB](https://user-images.githubusercontent.com/58959408/174731448-b7b22a70-de87-4535-b8aa-3fb3294c9661.png)

## 5. First boot

After installation finishes, reboot and remove the ISO from the virtual optical drive if VirtualBox does not do so automatically. At boot:

1. Select **Debian GNU/Linux**.
2. Enter the encryption passphrase.
3. Log in with the normal user.
4. Inspect the storage layout:

```bash
lsblk
findmnt
```

The output should show the encrypted and LVM layers required by the subject.

# Part 4 - Configure the Server

## 1. Install and configure `sudo`

Switch to a root shell only for the initial installation:

```bash
su -
apt update
apt-get install sudo
```

Add the normal user to the Debian administrative group:

```bash
usermod -aG sudo <login>
getent group sudo
```

Restart the login session, or reboot, before testing the new group membership. Confirm that the normal user can use `sudo`:

```bash
sudo -v
sudo whoami
```

The second command should print `root`. This does not mean the user has become root permanently; it means the individual command was executed with elevated privileges.

Use `visudo` only when the subject requires a direct edit to the main sudoers file. It validates the syntax before saving and is safer than editing `/etc/sudoers` with a normal editor.

## 2. Optional development tools

Git and Vim are useful tools, but they are not security requirements of Born2beRoot. Install only what your workflow needs:

```bash
sudo apt install git vim

git --version
vim --version
```

## 3. Configure the hostname

Check the current hostname and update it only if necessary:

```bash
hostnamectl
sudo hostnamectl set-hostname <hostname>
```

If the hostname changes, inspect `/etc/hosts` and update the local hostname entry consistently:

```bash
sudo nano /etc/hosts
```

Reboot or start a new session after changing the hostname, then verify it with `hostnamectl`.

# Part 5 - Connect Through SSH

SSH provides an encrypted channel for remote administration. In Born2beRoot, the configuration demonstrates service installation, port management, access restriction, and the prohibition of direct root login.

## 1. Install and configure the SSH server

```bash
sudo apt update
sudo apt install openssh-server
sudo systemctl enable --now ssh
sudo systemctl status ssh
```

Edit the daemon configuration:

```bash
sudo vim /etc/ssh/sshd_config
```

Set the port required by the subject and disable direct root login:

```text
Port 4243
PermitRootLogin no
```

Remove the leading `#` when the line is commented. Validate the configuration before restarting the daemon:

```bash
sudo sshd -t
sudo systemctl restart ssh
sudo ss -tulpn | grep 4242
```

Keep the VM console or an existing SSH session open until a new connection has been tested successfully.

## 2. Configure VirtualBox port forwarding

Power off the VM before changing its network settings. Open **Settings → Network → Adapter 1 → Advanced → Port Forwarding** and create a rule similar to this:

| Field | Value |
|---|---|
| Name | `SSH-4242` |
| Protocol | `TCP` |
| Host IP | `127.0.0.1` |
| Host port | `4242` |
| Guest IP | Leave empty unless required by your network configuration. |
| Guest port | `4242` |

Binding the host side to `127.0.0.1` keeps the forwarding local to the host computer. Do not expose the VM to the public network unless the subject explicitly requires it.

![VirtualBox port-forwarding settings](https://user-images.githubusercontent.com/58959408/174720900-39eda7e0-9be8-453c-94f1-4aa1a6b10951.png)

![Forward host port 4242 to guest port 4242](https://user-images.githubusercontent.com/58959408/174720987-e8de3bf9-2ffa-40ca-9d5c-4d0dea9d0b30.png)

## 3. Test the SSH connection

Start the VM and connect from the host terminal:

```bash
ssh <login>@127.0.0.1 -p 4242
```

When the VM is reinstalled, the SSH host key may change. Remove only the obsolete key for this endpoint rather than deleting the complete `known_hosts` file:

```bash
ssh-keygen -R '[127.0.0.1]:4242'
```

Exit the session with:

```bash
exit
```

## 4. Configure UFW

UFW is a simplified interface for firewall management. Install it and allow the SSH port before enabling the firewall:

```bash
sudo apt update
sudo apt install ufw
sudo ufw allow 4242/tcp
sudo ufw enable
sudo ufw status numbered
```

The order is important. Enabling UFW before allowing the management port can lock you out of the server. Allow only the ports required by the project.

Do not use `sudo ufw allow ssh` as the only rule when SSH has been moved to port `4242`; explicitly allow `4242/tcp` and verify the result.

# Part 6 - Apply Security and Automation

## 1. Enforce password quality with PAM

Install the password-quality module:

```bash
sudo apt install libpam-pwquality
```

Open the PAM password configuration:

```bash
sudo vim /etc/pam.d/common-password
```

Find the `pam_pwquality.so` line and add the options required by the subject. A typical configuration is:

```text
password requisite pam_pwquality.so retry=3 minlen=10 ucredit=-1 lcredit=-1 dcredit=-1 maxrepeat=3 reject_username difok=7 enforce_for_root
```

| Option | Meaning |
|---|---|
| `retry=3` | Allows three attempts to choose a valid password. |
| `minlen=10` | Requires at least ten characters. |
| `ucredit=-1` | Requires at least one uppercase letter. |
| `lcredit=-1` | Requires at least one lowercase letter. |
| `dcredit=-1` | Requires at least one digit. |
| `maxrepeat=3` | Limits repeated consecutive characters. |
| `reject_username` | Rejects a password containing the username. |
| `difok=7` | Requires a significant difference from the previous password. |
| `enforce_for_root` | Applies the quality rules when changing the root password. |

PAM is authentication-critical. Create a snapshot and keep a recovery path open before editing it. Test a controlled password change after saving the file.

## 2. Configure password aging

Edit `/etc/login.defs`:

```bash
sudo vim /etc/login.defs
```

Set the values required by the subject:

```text
PASS_MAX_DAYS   300
PASS_MIN_DAYS   2
PASS_WARN_AGE   7
```

These defaults mainly affect newly created accounts. Apply the values to an existing user explicitly when required:

```bash
sudo chage -M 30 -m 2 -W 7 <login>
sudo chage -l <login>
```

The `chage -l` command displays the active password-aging information and is useful during evaluation.

