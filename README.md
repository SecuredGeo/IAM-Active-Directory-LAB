# IAM-Active-Directory-LAB(on-Prem to Cloud)
🛡️ Active Directory IAM Homelab (Windows Server 2022)

This project simulates a real enterprise identity environment using Active Directory Domain Services (AD DS), DNS, Group Policy, and Role-Based Access Control (RBAC).
The goal of this lab is to demonstrate hands-on skills in Identity & Access Management, user provisioning, security hardening, and enterprise access controls.

🔰 1. Server Setup — Domain Controller Deployment
Windows Server Manager — Role Overview
<img width="1435" height="878" alt="Server manager dashboard" src="https://github.com/user-attachments/assets/381c5d21-e1ac-419c-b54f-1e696a7ae3ec" />

After installing Windows Server 2022, the machine was promoted to a Domain Controller for the domain homelab.local.
Core identity roles installed:

Active Directory Domain Services (AD DS)

DNS Server

File and Storage Services

These services form the backbone of identity authentication, directory management, and network resource access.

🏢 2. Organizational Unit (OU) Structure
Custom OU Structure for Departments
<img width="756" height="527" alt="Inside Orgs" src="https://github.com/user-attachments/assets/986afc0c-7f8c-44a5-88d9-d5073bb04313" />

Created a clean and scalable OU structure to reflect real enterprise departments:

HR

Interns

IT

Sales

Workstations

This layout supports targeted Group Policy Objects (GPOs), role-based access control, and lifecycle management.

👥 3. User Provisioning & RBAC
Creating New User Accounts
<img width="758" height="533" alt="Sarah Love USer" src="https://github.com/user-attachments/assets/919baab2-7033-46bf-a2a1-d2f6ef76c986" />

<img width="751" height="526" alt="Sarah Love Password" src="https://github.com/user-attachments/assets/f4269f36-f312-490c-8332-fc01fa7111cf" />



Provisioned users inside their appropriate OUs with secure password settings and first-login reset requirements.
IAM tasks demonstrated:

Creating new user identities

Assigning usernames (UPNs)

Enforcing password reset on first logon

Storing users in department-specific OUs

HR Users & Security Groups

Created security groups to enforce RBAC:

HR_Managers

HR_Staff

This allows access to be managed by roles, not individual accounts — a core IAM practice.

📂 4. Secure File Shares with NTFS & Share Permissions
HR Managers Folder (NTFS Permission Assignment)
<img width="947" height="552" alt="Hr managrs access" src="https://github.com/user-attachments/assets/501006c8-fd60-4a8d-8286-54ca479efcf2" />

Configured NTFS permissions to enforce least privilege:

HR_Managers → Full Control

Administrators → Full Control

Users → Read

HR Shared Department Folder

Assigned permissions to allow only HR employees to modify files:

HR_Staff → Modify / Write

Administrators → Full Control

Users → Read

This demonstrates real-world departmental access control.

File Share Overview (C:\ Drive)

Folders created for:

HR Managers

HR Shared

System and program files

These represent departmental network drives commonly used in organizations.

🔐 5. Password & Account Lockout Policies
Password Policy Configuration (Default Domain Policy)
<img width="733" height="812" alt="Policy requirements" src="https://github.com/user-attachments/assets/a4dc3dd2-8490-4fc1-99b7-bcd907ccabe6" />

Enforced enterprise password requirements:

Minimum length: 7 characters

Password complexity: Enabled

Maximum password age: 42 days

Password history: 24 remembered

Also reviewed lockout & Kerberos ticket policies for secure authentication.

🛡️ 6. Group Policy Objects (GPOs)
IT Security GPO — Linked to IT OU
<img width="754" height="530" alt="Group policy management" src="https://github.com/user-attachments/assets/59323a8f-9d01-4c10-92a8-bb14f14a663a" />

The “IT Security Policy” GPO was linked to the IT OU, applying customized security settings to only IT staff or computers inside that OU.

Delegation for GPO Access Control

Configured who can read, apply, and modify the policy:

Domain Admins / Enterprise Admins → Full access

Authenticated Users → Apply GPO

SYSTEM → Default machine-level permissions

This simulates administrative separation of duties.

🧠 7. IAM Concepts Demonstrated

This lab demonstrates core Identity & Access Management skills:

🔹 User Provisioning

Creating users, assigning roles, enforcing password resets.

🔹 Role-Based Access Control (RBAC)

Using security groups for permission assignments.

🔹 Organizational Unit (OU) Design

Separation of departments for easier policy application.

🔹 Group Policy Management

Implementing password policies, workstation security, and delegated administration.

🔹 NTFS & Share Permissions

Controlling file access using least-privilege principles.

🔹 Domain Services Infrastructure

DNS + AD DS working together for authentication.

🏁 8. Summary

This Active Directory homelab simulates an enterprise identity environment where I practiced:

Identity creation and lifecycle management

Access provisioning using RBAC

Security hardening with Group Policy

Departmental file access management

On-premises directory administration

This project showcases hands-on experience that directly aligns with IAM Analyst, Active Directory Administrator, and IT Security roles.
