# windows-server-active-directory-lab
Active Directory Domain Services lab demonstrating Windows Server domain configuration, user and group management, organizational units, and Group Policy.

## Project Overview

This project documents the configuration and administration of a Windows Server Active Directory environment built using Oracle VirtualBox. The lab consists of two Windows Server 2025 virtual machines and one Windows 11 client, which were configured to communicate over a shared virtual network.

The project progresses from initial system and network configuration into Active Directory Domain Services (AD DS) and DNS deployment, domain controller configuration, domain enrollment, user and organizational unit management, authentication testing, scheduled task administration, and PowerShell scripting.

The goal of the lab was to develop practical experience with Windows Server administration, Active Directory, domain-based authentication, task scheduling, and PowerShell automation in a controlled virtual environment.


## Lab Environment

This project was completed in a virtualized environment using Oracle VirtualBox.

### Virtual Machine Environment

The lab environment consists of 3 virtual machines:
-Two Windows Server 2025 virtual machines
-One Windows 11 client virtual machine

### Operating Systems

- **KH-SP26-S25-S1** — Windows Server 2025
- **KH-SP26-S25-S2** — Windows Server 2025
- **KH-SP26-W11-C1** — Windows 11


## 1. Initial Environment Configuration

### Operating System Installation

Windows Server 2025 was installed on both server virtual machines, while Windows 11 was installed on the client virtual machine.

### Network Configuration

IP configuration was verified on all three virtual machines using `ipconfig /all`.

### Network Connectivity Verification

Connectivity between the three virtual machines was verified using `ping`.



## 2. Active Directory Domain Services

### AD DS and DNS Installation

Active Directory Domain Services and DNS roles were installed on the primary Windows Server.

### Domain Controller Configuration

The primary Windows Server was configured as a domain controller for the `savn.local` domain.

### Domain Configuration

The server was configured within the `savn.local` Active Directory domain.

### Domain Computer Enrollment

The secondary Windows Server and Windows 11 client were joined to the `savn.local` domain.

### Active Directory Computer Objects

The domain-joined computers were verified within Active Directory.



## 3. System Administration

### Organizational Units

Organizational Units were created within the `savn.local` Active Directory environment to organize domain objects.

### Local User Accounts

A local user account was created and used to demonstrate local authentication on a domain-connected system.

### Domain User Accounts

A domain user account was created within Active Directory and assigned to the appropriate Organizational Unit.

### Local vs. Domain Authentication

Local and domain user accounts were used to demonstrate the difference between local authentication and authentication through the Active Directory domain.

### Domain Availability and Authentication

Domain authentication behavior was tested when the domain server was unavailable.



## 4. Task Scheduling and PowerShell Scripting

### Scheduled Task Creation

Scheduled tasks were created and configured using Windows Task Scheduler.

### Task Triggers and Actions

Task triggers and actions were configured to control when scheduled tasks execute and what actions they perform.

### Task Execution

A scheduled task was configured to execute under the `domainUser01` account on the domain-connected system.

### Remote Task Verification

The scheduled task was verified on the remote system and confirmed to be running under the expected domain account.

### PowerShell-Scripted Task

A `displayDateMessage` task was created to demonstrate scheduled execution of a PowerShell-based action.

### Task Registration and Execution

The PowerShell-based task was registered in the Task Scheduler library and its execution was verified.



## Skills Demonstrated

## Future Work

## Conclusion
