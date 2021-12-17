# Lab 1: Create a Linux virtual machine with the Azure CLI

1. Launch Azure Cloud Shell
2. Create a resource group
3. Create virtual machine
4. Open port 80 for web traffic
5. Connect to virtual machine
6. Install web server
7. View the web server in action

### Notes:

Quickstart: Create a Linux VM
* https://docs.microsoft.com/en-us/azure/virtual-machines/linux/quick-create-cli

Quickstart for Bash in Azure Cloud Shell
* https://docs.microsoft.com/en-us/azure/cloud-shell/quickstart

# Procedures
# Launched the azure cloud shell and created a resource group in Azure with the command 
az group create --name MyRg1 --location eastus
# Create machine was created with the command 
az vm create 
--resource-group MyRg1 
--name MyVm1 
--image UbuntuLTS 
--admin-username azureuser 
--generate-ssh-keys
# Copied the public ip address of the vertual machine
# Thirdly, Open port with the command 
az vm open-port 
--port 80 
--resource-group MyRg1 
--name MyVm1
# Fourthly, connect to the virtual machine 
ssh azureuser@20.120.85.144

# Then, I used root user command to update and install web server
sudo apt-get -y update 
sudo apt-get -y install nginx
# Lastly, I tested the webserver and then exited.


