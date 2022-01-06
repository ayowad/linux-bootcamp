# Lab 1: Install a LAMP stack on an Azure Linux VM

1. Create a resource group
2. Create a virtual machine
3. Open port 80 for web traffic
4. SSH into your VM
5. Install Apache, MySQL, and PHP
6. Install WordPress

### Notes:

Tutorial: Install a LAMP stack on an Azure Linux VM
* https://docs.microsoft.com/en-us/azure/virtual-machines/linux/tutorial-lamp-stack

Sample Gist
* https://gist.github.com/mikepfeiffer/96d659042f0575a617648a33c92b8f4a

Build and run a web application with the MEAN stack on an Azure Linux virtual machine
* https://docs.microsoft.com/en-us/learn/modules/build-a-web-app-with-mean-on-a-linux-vm/

MEAN Stack App
* https://github.com/MicrosoftDocs/mslearn-build-a-web-app-with-mean-on-a-linux-vm



# Created a Resource Group
az group create --resource-group lampstack-rg --location eastus

# Create a VM
az vm create --resource-group lampstack-rg --name lampstack-vm
--image UbuntuLTS
--admin-user azureuser
--generate-ssh-keys

output:
{
  "fqdns": "",
  "id": "/subscriptions/f6db755a-1490-42f1-be1c-adbb1d7328b1/resourceGroups/lamp
stack-rg/providers/Microsoft.Compute/virtualMachines/lampstack-vm",
  "location": "eastus",
  "macAddress": "00-22-48-2A-C8-91",
  "powerState": "VM running",
  "privateIpAddress": "10.0.0.4",
  "publicIpAddress": "13.92.159.153",
  "resourceGroup": "lampstack-rg",
  "zones": ""

# Open web traffic port
az vm open-port --port 80 --name lampstack-vm --resource-group lampstack-rg



#ssh into the vm
ssh azureuser@13.92.159.153

# Install Apache, MySQL, and PHP
sudo apt update && sudo apt install lamp-server^


# Install WordPress
sudo apt install wordpress
# configure WordPress 
sudo sensible-editor wordpress.sql

creating a database with accessibility and identified by a password
CREATE DATABASE wordpress;
GRANT SELECT,INSERT,UPDATE,DELETE,CREATE,DROP,ALTER
ON wordpress.*
TO wordpress@localhost
IDENTIFIED BY 'yourPassword';

