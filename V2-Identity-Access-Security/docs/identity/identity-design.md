# Identity Design

## 1. Purpose

The purpose of this design is to define how identities and access will be managed in the Azure environment for V2.

The project follows the principle of least privilege, where users receive only the permissions required for their responsibilities.

---

## 2. Identity Architecture

The V2 environment uses Microsoft Entra ID as the identity layer.

Users are organized into groups based on their responsibilities. Azure RBAC is then used to control access to Azure resources.

```text
                    Microsoft Entra ID
                           |
                    Users + Groups
                           |
                           v
                       Azure RBAC
                           |
                    Least Privilege
                           |
                           v
                    Azure Resources
