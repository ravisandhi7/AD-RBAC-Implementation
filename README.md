# 🔐 AD-RBAC-Implementation

## 📌 Overview

This project demonstrates **Role-Based Access Control (RBAC)** implementation using **Active Directory** and **NTFS permissions** in a Windows Server environment.

The goal is to ensure that users can only access resources based on their job roles (HR_Dept, IT_Dept, Finance_Dept).


## 🏗️ Lab Environment


* Windows Server (Domain Controller / ROOTDC Name- Server1)


* Active Directory Domain Services (AD DS)


* File Server with shared folders


* Domain-joined client machine(PC1)


## 📂 Active Directory Structure


### Organizational Units (OUs)


* HR_Dept


* IT_Dept


* Finance_Dept


* Security_Groups

![OU_CREATED](screenshots/OU_USERS_GROUPS/OU_CREATED.png)


## 👥 Users


### HR_Dept


* hrdept1


* hrdept2

![HRDEPT_USERS](screenshots/OU_USERS_GROUPS/HRDEPT_USERS.png)


### IT_Dept

* itdept1

* itdept2

![ITDEPT_USERS](screenshots/OU_USERS_GROUPS/ITDEPT_USERS.png)


### Finance_Dept

* financedept1

* financedept2

![FINANCEDEPT_USERS](screenshots/OU_USERS_GROUPS/FINANCEDEPT_USERS.png)


## 🔐 Security Groups (RBAC Roles)

* HR_Access

* IT_Admins

* Finance_Access

* Shared_Access


## RBAC Mapping

| Department      | Users                      | Group          | Access         |
| ----------      | ------------               | -------------- | -------------- |
| HR_Dept         | hrdept1, hrdept2           | HR_Access      | HR Folder Only |
| IT_Dept         | itdept1, itdept2           | IT_Admins      | IT Folder Only |
| Finance_Dept    | financedept1, financedept2 | Finance_Access | Finance Folder |

![SECURITY_GROUPS](screenshots/OU_USERS_GROUPS/SECURITY_GROUPS.png)

![HR_ACCESS_MEMBERS](screenshots/OU_USERS_GROUPS/HR_ACCESS_MEMBERS.png)

![IT_ADMINS_MEMBERS](screenshots/OU_USERS_GROUPS/IT_ADMINS_MEMBERS.png)

![FINANCE_ACCESS_MEMBERS](screenshots/OU_USERS_GROUPS/FINANCE_ACCESS_MEMBERS.png)

![SHARED_ACCESS_MEMBERS](screenshots/OU_USERS_GROUPS/SHARED_ACCESS_MEMBERS.png)


## 📁 Folder Structure

C:\CompanyData\

* HR

* IT

* Finance

* Shared

![COMPANY_DATA_FOLDERS](screenshots/OU_USERS_GROUPS/COMPANY_DATA_FOLDERS.png)


## 🔐 Permissions Design

### NTFS Permissions

* HR → HR_Access (Modify)

![HR_ACCESS_PERMISSIONS](screenshots/NTFS/HR_ACCESS_PERMISSIONS.png)


* IT → IT_Admins (Modify)
  
![IT_ADMINS_PERMISSIONS](screenshots/NTFS/IT_ADMINS_PERMISSIONS.png)

* Finance → Finance_Access (Modify)

![FINANCE_ACCESS_PERMISSIONS](screenshots/NTFS/FINANCE_ACCESS_PERMISSIONS.png)

* Shared → Shared_Access (Modify)

![SHARED_ACCESS_PERMISSIONS](screenshots/NTFS/SHARED_ACCESS_PERMISSIONS.png)



### Share Permissions

* Configured using respective security groups

* Full Control granted at share level

* Final access controlled by NTFS (most restrictive)

![HR_ACCESS_SHARING](screenshots/Share_permissions/HR_ACCESS_SHARING.png)

![IT_ADMINS_SHARING](screenshots/Share_permissions/IT_ADMINS_SHARING.png)

![FINANCE_ACCESS_SHARING](screenshots/Share_permissions/FINANCE_ACCESS_SHARING.png)

![SHARED_ACCESS_SHARING](screenshots/Share_permissions/SHARED_ACCESS_SHARING.png)



## 🧪 Access Testing (Proof of RBAC)

### HR Users

* Access HR_Share → ✅ Allowed
 
![HRDEPT_TO_HR_SHARE_WORK](screenshots/verification/HRDEPT_TO_HR_SHARE_WORK.png)


* Access Finance_Share → ❌ Denied

![HRDEPT_TO_FINANCE_SHARE_DENY](screenshots/verification/HRDEPT_TO_FINANCE_SHARE_DENY.png)

![HRDEPT](screenshots/verification/HRDEPT_verification_all.png)

![HRDEPT](screenshots/verification/HRDEPT_verification_all_CONTD.png)


### IT Users

* Access IT_Share → ✅ Allowed

![ITDEPT_TO_IT_SHARE_WORK](screenshots/verification/ITDEPT_TO_IT_SHARE_WORK.png)

* Access HR_Share → ❌ Denied

![ITDEPT_TO_HR_SHARE_DENY](screenshots/verification/ITDEPT_TO_HR_SHARE_DENY.png)

![ITDEPT](screenshots/verification/ITDEPT_verification.png)


![ITDEPT](screenshots/verification/ITDEPT_verification_all.png)


### Finance Users

* Access Finance_Share → ✅ Allowed
  
![FINANCEDEPT_TO_FINANCE_SHARE_WORK](screenshots/verification/FINANCEDEPT_TO_FINANCE_SHARE_WORK.png)

* Access IT_Share → ❌ Denied
  
![FINANCEDEPT_TO_IT_SHARE_DENY](screenshots/verification/FINANCEDEPT_TO_IT_SHARE_DENY.png)


![FINANCEDEPT](screenshots/verification/FINANCEDEPT_verification_all.png)


![FINANCEDEPT](screenshots/verification/FINANCEDEPT_verification_all_CONTD.png)


### Shared Folder

* Accessible by all users → ✅
## HR Users
![HRDEPT_TO_SHARED_SHARE_WORK](screenshots/verification/HRDEPT_TO_SHARED_SHARE_WORK.png)

## IT Users
![ITDEPT_TO_SHARED_SHARE_WORK](screenshots/verification/ITDEPT_TO_SHARED_SHARE_WORK.png)

## Finance Users
![FINANCEDEPT_TO_SHARED_SHARE_WORK](screenshots/verification/FINANCEDEPT_TO_SHARED_SHARE_WORK.png)


## 💡 Key Concepts Demonstrated

* Role-Based Access Control (RBAC)

* Active Directory user & group management

* NTFS vs Share permissions

* Principle of Least Privilege

* Access verification and testing

## 🚀 Outcome

Successfully implemented a secure, scalable access control model where:

* Users are assigned roles via groups

* Permissions are managed centrally

* Unauthorized access is prevented

## 📚 Skills Gained

* Windows Server Administration

* Active Directory Management

* File Server Configuration

* Security & Access Control

* Troubleshooting Permissions

## 🧠 Author

Ravi Kumar
