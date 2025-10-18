# 4 Active Directory Basics

## 4.2 Windows Domains
- **windows domain** is a group of users and computers under the administration of a given business.
- this is to centralize the administraions common components of a Windows computer network in a single repository called `Active Directory`.
- while the server that runs the **Active Directory** services is called `Domain Controller (DC)`.
- advantages of having config windows domain:
    - **Centralized Identity Management** all users across the network can be configured from the `Active Directory`.
    - **Managing Security Policies** can config security policies directly from the `Active Directory` and apply them to users and computers across the network as needed.

## 4.3 Active Directory
- `Active Directory Domain Service (AD DS)` is the core of any Windows Domain.
    - acts as the service catalogue that holds information of all `objects` that exist in your network.
    - `objects` supported are: `users, groups, machines, printers, shares, and many others.`

### Users
- one of the most common object types.
- the ones known as `security principals` - they can be authenticated by the domain and assigned privileges over resources like files or printers.
- Users represents two entities:
    - `People` represent persons in an organization.
    - `Services` represents persons that can run specific services within the organization.

### Machines
- also considered as `security principals` and are assigned an account just like a regular user.
- somewhat have limited rights over the domain.
- machine account name is the computer's name followed by a dollar sign. Ex. machine named `PC-TOM` will have a machine account called `PC-TOM$`.

### Security Groups
- also considered as `security principals`, therefore have privileges over resources in the network.
- for better management of access rights for user groups.
- default groups in the domain:
    - `Domain Admins` administrative privileges over the domain. Can administer any computer, including the DC.
    - `Server Operators` can administer DC. Cannot change administrative group memberships.
    - `Backup Operators` allowed to access any file, ignoring permissions. Used to perform backups of data on computers.
    - `Account Operators` can create or modify accounts in the domain.
    - `Domain Users` all existing user accounts in the domain.
    - `Domain Computers` all existing computers in the domain.
    - `Domain Controllers` all existing DCs in the domain.

### Active Directory Users and Computers
- `Organizational Units (OU)` container objects that allows you to classify users and machines.
    - mainly used to define set of users with similar policy requirements.

### Security Groups vs Organizational Units
- `OUs` are handy for `applying policies` to users and machines. A user can only be a member of one OU at a time.
- `Security Groups` used to `grant permissions over resources`. A user can be a part of many security groups (be able to have access to multiple resourcess).

## 4.4 Managing Users in AD

### Deleting extra OUs and Users
- by default, OUs are protected against `accidental deletion`.
- find `Advanced Features` in View menu, then under `Object tab` disable the object protection.

## Delegation
- this process allows you to give specific users some control over the OUs.
- grants selected users to have specific privilege without needing an Domain Admin to step in (most common in `IT Support`).
- to delegate control over an OU, right-click it and select `Delegate Control`.
