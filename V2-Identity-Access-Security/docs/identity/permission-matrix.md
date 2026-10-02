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

Entra ID Group	                  RBAC     Role	    Scope	                                Purpose
Cloud-Developers	                To be finalized	  V2 Resource Group / Resource	        Development operations
Security-Team	                    To be finalized	  V2 Resource Group / Resource	        Security inspection and validation
Cloud-Administrators	            To be finalized	  V2 Resource Group	                    Infrastructure administration

The exact built-in Azure RBAC roles will be selected and justified before implementation.

## 4. Access Requirements
Cloud-Developers

Required capabilities:

Work with resources required for development
Inspect relevant resource configuration
Perform necessary development operations
No unnecessary identity-management privileges
No unnecessary subscription-level administrative access
Security-Team

Required capabilities:

Inspect Azure resources
Review security configuration
Validate network and infrastructure security
Perform security-related checks
No unnecessary infrastructure-management privileges
Cloud-Administrators

Required capabilities:

Manage the V2 infrastructure
Create and modify required Azure resources
Troubleshoot infrastructure
Perform administrative operations required by the project


## 5. Privilege Boundaries

The following boundaries will be maintained:

Group	Should NOT automatically receive
Cloud-Developers	Tenant-wide administrative access
Security-Team	Broad infrastructure modification access
Cloud-Administrators	Unnecessary tenant-wide identity privileges


## 6. Assignment Principles

RBAC assignments will follow these rules:

Prefer group-based assignments over individual assignments.
Use the narrowest practical scope.
Avoid Owner unless explicitly required.
Avoid subscription-wide access when resource-group or resource-level access is sufficient.
Use built-in Azure roles where they satisfy the requirement.
Document the reason for each role assignment.
Validate both allowed and denied operations.


## 7. Implementation Status

Current status:

 Identity groups defined
 RBAC responsibilities defined
 Resource scope identified
 Exact RBAC roles selected
 RBAC assignments implemented
 Access tested
 Evidence captured

### Important
```
Notice that I left **"To be finalized"** instead of inventing roles now.

That's intentional. We should select the actual Azure built-in roles based on the operations we want each group to perform, then document why each role was chosen.

Once this file is saved, **the identity design phase is complete**. The next step will be selecting the actual RBAC roles and then moving into the architecture design.
```
