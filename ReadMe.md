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

Screenshot 1: Output of systeminfo

2️⃣ User Management
2.1 Objective

To create and manage local user accounts using PowerShell.

2.2 Create New User
net user student1 Password123 /add
Result:

The command completed successfully, creating a new local account named student1.

Screenshot 2: User creation confirmation

2.3 Verify Administrator Group
net localgroup administrators

This command lists members of the Administrators group.

Observation:

Administrator

Capaciti

An attempt to add another user resulted in a domain trust error, indicating the system is domain-connected.

Explanation:

The error occurred because the workstation is joined to a domain, and the trust relationship with the primary domain failed.

Screenshot 3: Administrator group listing

3️⃣ File System Management
3.1 Objective

To create a directory and manage NTFS permissions.

3.2 Create a Folder
mkdir C:\PowerUserTest

Screenshot 4: Folder creation

3.3 Assign Permissions
icacls C:\PowerUserTest /grant student1:F
Permission Meaning:

F = Full Control

To verify permissions:

icacls C:\PowerUserTest
Result:

The user student1 was successfully granted Full Control over the directory.

Screenshot 5: Permission configuration

3.4 Explanation

Windows uses the NTFS file system, which manages security through Access Control Lists (ACLs).

The icacls command modifies file and folder permissions by updating ACL entries. This demonstrates understanding of:

NTFS security

Access Control Entries (ACEs)

User-based access control

4️⃣ Package Management (Command Line Installation)
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

Screenshot 6: Installation output

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

In this practical task, PowerShell was used to perform administrative operations including system information retrieval, user creation, permission configuration, and software installation.

The exercise demonstrates the role of the operating system in managing hardware resources, users, memory, file systems, and installed applications.

Conclusion

This task provided practical experience in Windows system administration and reinforced key operating system concepts. Through the use of PowerShell, I successfully gathered system information, managed user accounts and permissions, controlled access to files using NTFS, and installed software via Chocolatey. The exercise strengthened my understanding of how the operating system manages hardware, users, processes, and applications, helping me develop essential Power User skills.