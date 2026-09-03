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

IP configuration was verified on all three virtual machines using `ipconfig /all`. This was used to confirm the network settings of the two Windows Server 2025 systems and the Windows 11 client before configuring the Active Directory environment.

<br>

![Windows 11 IP Configuration](screenshots/01-environment-setup/01-windows11-ipconfig.png)

![Server 1 IP Configuration](screenshots/01-environment-setup/02-server1-ipconfig.png)

<br><br>

### Network Connectivity Verification

Connectivity between the three virtual machines was verified using `ping`. Each system successfully communicated with the other two virtual machines, confirming network connectivity before proceeding with domain and Active Directory configuration.

<br>

![Server 1 Connectivity](screenshots/01-environment-setup/03-server1-connectivity.png)

<br><br>

## 2. Active Directory Domain Services

### AD DS and DNS Installation

Active Directory Domain Services and DNS roles were installed on the primary Windows Server.

<br>

![AD DS and DNS Installed](screenshots/02-active-directory-domain-services/01-ad-ds-dns-installed.png)

<br><br>

### Domain Controller Configuration

The primary Windows Server was configured as a domain controller for the `savn.local` domain.

<br>

![Domain Controller Configured](screenshots/02-active-directory-domain-services/02-domain-controller-configured.png)

<br><br>

### Domain Configuration

The domain controller was configured for the `savn.local` domain, establishing the Active Directory environment used throughout the remainder of the lab.

### Domain Computer Enrollment

The secondary Windows Server and Windows 11 client were joined to the `savn.local` domain.

<br>

![Server 2 Joined Domain](screenshots/02-active-directory-domain-services/03-server2-joined-domain.png)

![Windows 11 Joined Domain](screenshots/02-active-directory-domain-services/04-windows11-joined-domain.png)

<br><br>

### Active Directory Computer Objects

The domain-joined computers were verified as computer objects within the `savn.local` Active Directory environment.

<br>

![Domain Computers in Active Directory](screenshots/02-active-directory-domain-services/05-domain-computers-in-ad.png)

<br><br>



## 3. System Administration

### Organizational Units

Organizational Units were created within the `savn.local` Active Directory environment to organize and manage domain objects.

<br>

![Organizational Units](screenshots/03-system-administration/01-organizational-units.png)

<br><br>

### Local User Accounts

A local user account was created on a domain-connected Windows Server system and used to demonstrate local authentication and account management.

<br>

![Local User Created](screenshots/03-system-administration/02-local-user-created.png)

<br><br>

### Domain User Accounts

A domain user account was created within Active Directory and assigned to the appropriate Organizational Unit.

<br>

![Domain User in Administration OU](screenshots/03-system-administration/03-domain-user-in-administration-ou.png)

<br><br>

### Local vs. Domain Authentication

Local and domain user accounts were used to demonstrate the difference between local authentication and authentication through the Active Directory domain.

<br>

![Local User Authentication](screenshots/03-system-administration/04-local-user-authentication.png)

![Domain User Authentication](screenshots/03-system-administration/05-domain-user-authentication.png)

<br><br>

### Domain Availability and Authentication

Domain authentication was tested while the domain server was unavailable to observe how domain-based login behavior is affected when the domain controller cannot be reached.

<br>

![Domain Authentication Server Unavailable](screenshots/03-system-administration/06-domain-authentication-server-unavailable.png)

<br><br>


## 4. Task Scheduling and PowerShell Scripting

### Scheduled Task Creation

Scheduled tasks were created using Windows Task Scheduler and configured with specific triggers and actions.

<br>

![Start Notepad Task General](screenshots/04-task-scheduling-powershell/01-startnotepad-general.png)

<br><br>

### Task Triggers and Actions

Task triggers and actions were configured to control when scheduled tasks execute and what actions they perform.

<br>

![Start Notepad Task Trigger](screenshots/04-task-scheduling-powershell/02-startnotepad-trigger.png)

![Start Notepad Task Action](screenshots/04-task-scheduling-powershell/03-startnotepad-action.png)
<br><br>


### Task Execution

A scheduled task was configured to execute under the `domainUser01` account on `KH-SP26-S25-S2` and its execution was verified.

<br>

![Start Notepad Task Execution](screenshots/04-task-scheduling-powershell/04-startnotepad-execution.png)

<br><br>

### Remote Task Verification

The scheduled task was verified on the remote `S2` system and confirmed to be running under the expected domain account.

<br>

![Start Notepad Remote Registration](screenshots/04-task-scheduling-powershell/05-startnotepad-remote-registration.png)

<br><br>

### PowerShell-Scripted Task

A `displayDateMessage` task was created using a PowerShell-based action. The task was configured with a defined trigger and action to automate execution.

<br>

![Display Date Message Trigger](screenshots/04-task-scheduling-powershell/06-displaydatemessage-trigger.png)

![Display Date Message Action](screenshots/04-task-scheduling-powershell/07-displaydatemessage-action.png)

<br><br>

### Task Registration and Execution

The PowerShell-based task was verified as registered in the Task Scheduler library and its execution was confirmed.

<br>

![Display Date Message Registration](screenshots/04-task-scheduling-powershell/08-displaydatemessage-registration.png)

![Display Date Message Execution](screenshots/04-task-scheduling-powershell/09-displaydatemessage-execution.png)

<br><br>



## Skills Demonstrated

- **Windows Server 2025 Administration** — Installation, configuration, and management of Windows Server virtual machines
- **Active Directory Domain Services (AD DS)** — Domain controller deployment, domain configuration, computer enrollment, user account management, and Organizational Unit management
- **DNS** — DNS role installation and configuration as part of the Active Directory environment
- **Network Configuration & Troubleshooting** — IP configuration, virtual network setup, and connectivity verification using `ipconfig` and `ping`
- **User & Authentication Management** — Local and domain user creation, domain-based authentication, and authentication testing during domain controller unavailability
- **Windows Task Scheduler** — Scheduled task creation, trigger/action configuration, remote task registration, and task execution
- **PowerShell** — PowerShell-based task automation and scripted task execution
- **Virtualization** — Oracle VirtualBox virtual machine deployment and management


## Potential Extensions

These are areas I could explore to further expand the existing lab environment and build on the skills demonstrated in this project. Future additions would focus on strengthening security, expanding Active Directory management, and gaining hands-on experience with network traffic analysis.

- **Additional Security Layers** — Expand the lab with additional security hardening, access controls, auditing, and security configurations.
- **Advanced Active Directory Management** — Expand user and group management, permissions, Group Policy, and other Active Directory administration tasks.
- **Network Traffic Analysis** — Use Wireshark to capture and analyze network traffic between the domain controller, servers, and client to examine protocols such as DNS and authentication traffic.



## Conclusion

This project provided hands-on experience building and administering a Windows Server Active Directory environment in a virtualized network. Through configuring AD DS and DNS, managing users and organizational units, testing authentication, and creating scheduled tasks with PowerShell, I developed practical experience with Windows Server administration, Active Directory, and system automation.
