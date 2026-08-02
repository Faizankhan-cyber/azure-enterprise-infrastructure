Day 01 - Azure Mega Project (Version 1)

Date: 2 August 2026

Project: Azure Secure Web Server (Version 1)

What I Built Today

Today I successfully deployed my first Linux virtual machine on Microsoft Azure and configured it as a basic web server.

Tasks Completed
Created a Resource Group for the project.
Created a Virtual Network (VNet).
Created a Subnet.
Created a Network Security Group (NSG).
Configured inbound security rules for SSH (22) and HTTP (80).
Deployed an Ubuntu Server 24.04 LTS Virtual Machine.
Generated and downloaded SSH key pair.
Connected to the VM securely using SSH from my Windows machine.
Installed and configured the Nginx web server.
Enabled the Nginx service to start automatically.
Verified that Nginx was listening on port 80.
Diagnosed networking issues preventing public access.
Attached the correct Network Security Group and verified inbound rules.
Successfully accessed the default Nginx webpage using the VM's public IP address.
Problems I Faced
SSH key permission errors on Windows.
Port 22 initially inaccessible.
HTTP requests timed out because of network configuration.
Accidentally tried accessing the server using HTTPS instead of HTTP, which caused connection failures until the issue was identified.
What I Learned
How Azure networking components work together (Resource Groups, VNets, Subnets, NSGs, Public IPs, and Virtual Machines).
How to connect to Linux servers using SSH keys.
Basic Linux server administration.
Installing and managing services using systemctl.
How Network Security Groups control inbound traffic.
The difference between HTTP (port 80) and HTTPS (port 443).
A structured approach to troubleshooting cloud networking issues.
Current Project Status

✅ Azure infrastructure deployed.

✅ Linux VM running successfully.

✅ Nginx web server installed and accessible over the internet.

⏳ Next step: Replace the default Nginx page with my own portfolio website and complete Version 1 of the project.

Skills Practiced
Microsoft Azure
Virtual Machines
Azure Networking
Network Security Groups
Linux Administration
Ubuntu Server
SSH
Nginx
Cloud Troubleshooting
Infrastructure Deployment
Next Goal

Deploy my personal portfolio website to the Azure VM, document the architecture, and complete Version 1 of my Azure flagship cloud project.