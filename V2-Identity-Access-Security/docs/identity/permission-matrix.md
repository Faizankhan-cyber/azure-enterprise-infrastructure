# Permission Matrix

## 1. Purpose

This document defines the planned access permissions for the V2 Azure environment.

The matrix maps each Entra ID security group to the Azure RBAC role and resource scope required for its responsibilities.

The design follows the principle of least privilege.

---

## 2. Resource Scope

The V2 environment will use a dedicated resource group:

```text
V2 Resource Group
│
├── Virtual Network
├── Subnet
├── Network Security Group
├── Public IP
└── Linux Virtual Machine
```
The primary RBAC scope will therefore be the V2 resource group unless a narrower resource-level scope is required.


## 3. Planned Permission Matrix

| Entra ID Group       | RBAC Role                            | Scope             | Purpose                                                        |
| -------------------- | ------------------------------------ | ----------------- | -------------------------------------------------------------- |
| Cloud-Developers     | Virtual Machine Contributor + Reader | V2 Resource Group | Manage the project VM and inspect related Azure resources      |
| Security-Team        | Security Reader                      | V2 Resource Group | Review security configuration and security-related information |
| Cloud-Administrators | Contributor                          | V2 Resource Group | Manage the V2 Azure infrastructure                             |


The exact built-in Azure RBAC roles will be selected and justified before implementation.

## 4. Access Requirements

#### Cloud-Developers

Required capabilities:

Work with resources required for development
Inspect relevant resource configuration
Perform necessary VM management operations
No unnecessary identity-management privileges
No unnecessary subscription-level administrative access

#### Security-Team

Required capabilities:

Inspect Azure resources
Review security configuration
Validate network and infrastructure security
Perform security-related checks
No unnecessary infrastructure-management privileges

#### Cloud-Administrators

Required capabilities:

Manage the V2 infrastructure
Create and modify required Azure resources
Troubleshoot infrastructure
Perform administrative operations required by the project

## 5. Privilege Boundaries

The following boundaries will be maintained:
| Group                | Should NOT automatically receive            |
| -------------------- | ------------------------------------------- |
| Cloud-Developers     | Tenant-wide administrative access           |
| Security-Team        | Broad infrastructure modification access    |
| Cloud-Administrators | Unnecessary tenant-wide identity privileges |


## 6. Assignment Principles

RBAC assignments will follow these rules:

Prefer group-based assignments over individual assignments.
Use the narrowest practical scope.
Avoid Owner unless explicitly required.
Avoid subscription-wide access when resource-group or resource-level access is sufficient.
Use built-in Azure roles where they satisfy the requirement.
Document the reason for each role assignment.
Validate both allowed and denied operations.


## 7. Final Role Selection

#### Cloud-Developers

Roles:

Virtual Machine Contributor
Reader

Scope:

V2 Resource Group

The Virtual Machine Contributor role provides VM management capabilities without granting Azure RBAC role-assignment permissions. Reader provides read-only visibility into the remaining resources required for development and troubleshooting.

#### Security-Team

Role:

Security Reader

Scope:

V2 Resource Group

Security Reader provides security-focused visibility without granting general infrastructure management permissions.

#### Cloud-Administrators

Role:

Contributor

Scope:

V2 Resource Group

Contributor provides the infrastructure-management capabilities required for the project without automatically granting Azure RBAC role-assignment permissions.


## 8. Privileged Role Decision

The following roles are intentionally not assigned to the project groups:

Owner
User Access Administrator
Role Based Access Control Administrator

These roles are excluded because the project does not require the groups to manage Azure RBAC assignments themselves.


## 9. Implementation Status

 Identity groups defined - Completed
 RBAC responsibilities defined - Completed
 Resource scope identified - Completed
 Exact RBAC roles selected - Completed
 Role-selection rationale documented - Completed
 RBAC assignments implemented
 Access tested
 Evidence captured
