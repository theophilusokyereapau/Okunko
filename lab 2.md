#  Standard Operating Procedure For Virtual Linux Server for Web Application Testing 
---

## PURPOSE OF THE DOCUMENT
This SOP outlines the steps to set up a virtual Linux server for the purpose of web application testing. It ensures a consistent, secure, and efficient deployment.

---

## AUDIENCE
This document is intended for system administrators, DevOps engineers, and QA analysts responsible for setting up test environments for web applications.

---

## APPROVAL TABLE

| Version | Date       | Name                    | Designation |
|---------|------------|-------------------------|-------------|
| 1.0     | 2024-07-16 | Theophilus Apau      | Author      |
| 1.1     | 2024-07-17 | Emmanuel Opoku              | Reviewer    |
| 1.1     | 2024-07-18 | Abiba Sakor              | Approver    |

---

## SCOPE/OBJECTIVES
This SOP includes:
- Pre-deployment planning
- Virtual machine creation
- Linux installation
- Software configuration for testing
- Documentation of Virtual Machine

---

## ACCOUNTABILITY MATRIX

| Task/Steps                          | Responsible Person/Team | Emergency Contact | Non-Emergency Contact | Review/Approval     |
|------------------------------------|--------------------------|-------------------|------------------------|---------------------|
| Pre-deployment planning            | System Administrator     | Phone/Email       | Phone/Email            | IT Manager          |
| Virtual Machine Creation                        | Virtualization Team      | Phone/Email       | Phone/Email            | IT Ops Manager      |
| Linux Installation                 | System Administrator     | Phone/Email       | Phone/Email            | QA Manager          |
| Software configuration for testing  | QA Team                  | Phone/Email       | Phone/Email            | QA Manager          |
|Documentation of Virtual Machine    | Documentation Team       | Phone/Email       | Phone/Email            | Team Lead           |

---

## EXECUTION STEPS

### Step 1: Pre-deployment planning

- Determine the specific purpose of the virtual machine  (database, web server, scripting support).
- Select Linux distribution ( Ubuntu Server 22.04 LTS, Redhat linux Enterprise).
- Set the VM hostname 
- Determine the resource plan 
- Network: NAT or bridged mode, static IP (e.g. 192.168.122.100)

---

### Step 2: Virtual Machine Creation

- Launch virtualization platform (e.g. VirtualBox or VMware).
- Create a new VM:
  - OS: Linux (e.g. Ubuntu 64-bit)
  - Name: (e.g. `Linux-web-vm`)
  - Resources: (e.g.2 CPU, 4GB RAM, 40GB HDD)
- Attach Linux ISO for installation
- Configure Virtual Machine to Boot the ISO

---

### Step 3: Linux Installation and Configuration

- Power on the virtual machine
- Install the Linux OS (e.g. Ubuntu Server 22.04):
  - OpenSSH Server enabled
  - Configure the User: (e.g. `tester`, password: `Passw0rd`)
  - Disable root 
  - Start installation
----

### Step 4: Software configuration for testing
- Ensure the Linux operating system is successfully installed.
- Configure network: Set up static IP and DNS in `/etc/netplan/01-netcfg.yaml` and test network connectivity
- Update system in the bash terminal with:
  ``` sudo apt update && sudo apt upgrade -y ```
- Install the essential web packages in the bash terminal with:
  ``` sudo apt install apache2 php mysql-server php-mysql unzip git -y ``` and
 ``` sudo systemctl enable apache2 mysql ```
----

### Step 5: Documentation of Virtual Machine
- Record any error discovered during installation.
- Record any further steps discovered that need to be added to the SOP.
- update system documentation with the new virtual machine information.

## REVISION HISTORY

| Version | Date       | Chnages Made By        | Summary of Chamges |
|---------|------------|-------------------------|-------------|
| 1.0     | 2024-07-16 | Theophilus Apau      | Initial Release of Document|
| 1.1     | 2024-10-20 | Emmanuel Opoku              | step 4/modified |
| 1.2    | 2024-12-01 | Abiba Sakor              | step 5/added   |
