Operating Systems and You – Becoming a Power User
User & File Management Practical (Windows PowerShell)

Introduction

This practical assignment focuses on developing Power User skills in a Windows environment using PowerShell. The objective was to explore operating system internals, manage users and groups, configure NTFS file permissions, and install software using a command-line package manager. By performing these tasks on Microsoft Windows 10 Pro, I gained hands-on experience with system administration tools and core operating system functions such as process management, security control, and resource management.


1️⃣ System Information
1.1 Objective

To retrieve and analyze system-level information using PowerShell in order to understand operating system internals.

1.2 Command Used
systeminfo
1.3 Key Findings

Host Name: DESKTOP-279TG12

Operating System: Microsoft Windows 10 Pro

OS Version: 10.0.19045 Build 19045

System Type: x64-based PC

Processor: Intel64 Family 6 Model 158 ~3912 MHz

Installed RAM: 8 GB

Domain: bwb.org.za

1.4 Explanation

The systeminfo command retrieves detailed configuration data stored by the Windows operating system. This information includes hardware specifications, memory allocation, processor details, and installed updates.

This demonstrates how the OS interacts with hardware through the Hardware Abstraction Layer (HAL).


<img width="854" height="716" alt="system" src="https://github.com/user-attachments/assets/03659431-a231-4232-b46b-bc74b6e1e361" />

2️⃣ User Management
2.1 Objective

To create and manage local user accounts using PowerShell.

2.2 Create New User
net user student1 Password123 /add
Result:

The command completed successfully, creating a new local account named student1.

<img width="845" height="323" alt="creat a new user" src="https://github.com/user-attachments/assets/75b32a9c-57e0-434b-9031-fa6677b388da" />


2.3 Verify Administrator Group
net localgroup administrators

This command lists members of the Administrators group.

Observation:

Administrator

Capaciti

An attempt to add another user resulted in a domain trust error, indicating the system is domain-connected.

Explanation:

The error occurred because the workstation is joined to a domain, and the trust relationship with the primary domain failed.


<img width="844" height="206" alt="add user to group" src="https://github.com/user-attachments/assets/6ce51fa1-b9b5-4789-bbc1-ace8181f1392" />

3️⃣ File System Management
3.1 Objective

To create a directory and manage NTFS permissions.

3.2 Create a Folder
mkdir C:\PowerUserTest

<img width="845" height="323" alt="creat a new user" src="https://github.com/user-attachments/assets/b8932d74-2612-4f8a-858e-5f910f877797" />


3.3 Assign Permissions
icacls C:\PowerUserTest /grant student1:F
Permission Meaning:

F = Full Control

To verify permissions:

icacls C:\PowerUserTest
Result:

The user student1 was successfully granted Full Control over the directory.

<img width="847" height="192" alt="permissions" src="https://github.com/user-attachments/assets/abcc7fdb-91b8-4ebf-b3ac-8d4db690856c" />


3.4 Explanation

Windows uses the NTFS file system, which manages security through Access Control Lists (ACLs).

The icacls command modifies file and folder permissions by updating ACL entries. This demonstrates understanding of:

NTFS security

Access Control Entries (ACEs)

User-based access control

4️⃣ chocolate and packaging (Package Management) (Command Line Installation)

<img width="873" height="298" alt="install chocolatey" src="https://github.com/user-attachments/assets/03b469af-8a55-4898-85ce-a898b85b99b7" />

4.1 Objective

To install software using a command-line package manager.

4.2 Chocolatey Verification

Chocolatey was already installed on the system.

choco --version
4.3 Install VLC Media Player
choco install vlc -y
Result:

VLC was successfully installed at:

C:\Program Files\VideoLAN\VLC

<img width="862" height="396" alt="install packaging" src="https://github.com/user-attachments/assets/e9c9e7e9-037e-48e2-aeda-28826abfc316" />

4.4 Explanation

Chocolatey is a Windows package manager that automates:

Software download

Installation

Dependency management

Updates

This demonstrates knowledge of package management concepts similar to Linux systems using apt.

5️⃣ Operating System Concepts Demonstrated

This practical exercise demonstrated understanding of:

✔ User account management
✔ Group membership and domain interaction
✔ NTFS file system permissions
✔ Access Control Lists (ACLs)
✔ System hardware information retrieval
✔ Command-line package management
✔ PowerShell administrative control

6️⃣ Conclusion

This task provided practical experience in Windows system administration and reinforced key operating system concepts. Through the use of PowerShell, I successfully gathered system information, managed user accounts and permissions, controlled access to files using NTFS, and installed software via Chocolatey. The exercise strengthened my understanding of how the operating system manages hardware, users, processes, and applications, helping me develop essential Power User skills.
