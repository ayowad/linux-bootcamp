# Lab 2: Manage Linux VMs with the Azure CLI

1. Create resource group
2. Create virtual machine
3. Connect to VM
4. Understand VM images
5. Understand VM sizes
6. VM power states
7. Management tasks

### Notes:

Quickstart: Create a Linux VM
* https://docs.microsoft.com/en-us/azure/virtual-machines/linux/tutorial-manage-vm

Quickstart for Bash in Azure Cloud Shell
* https://docs.microsoft.com/en-us/azure/cloud-shell/quickstart

### Notes:

Quickstart: Create a Linux VM
* https://docs.microsoft.com/en-us/azure/virtual-machines/linux/tutorial-manage-vm

Quickstart for Bash in Azure Cloud Shell
* https://docs.microsoft.com/en-us/azure/cloud-shell/quickstart

# Procedures:
# created a resource group 
az group create 
--name myrg2 
--location eastus
# created a virtual machine 
az vm create 
--resource-group myrg2 
--name myvm2 
--image UbuntuLTS 
--admin-username azureuser 
--generate-ssh-keys

# Note: the public ip address was copied (20.120.85.144)
# connected to the created virtual machine 
ssh azureuser@20.120.85.144

# updated and installed updates using the super user command 
sudo apt-get -y updates
sudo apt-get -y install nginx

# Then I used the command
az vm image list 
# to view the different types of images and understand how to implement them as appropriate
# Used the command to know the disk size of virtual machines

az vm list-sizes 
--location eastus 
--output table
# To know the power state of a virtual machine

az vm get-instance-view 
--resource-group MyRg1 
--name MyVm1 
--query instanceView.statuses[1] 
--output table

# I get to know if the virtual machine is running, stopped, deallocated etc
# I also performed virtual machine management task like starting, stopping, deallocation task

az vm start --resource-group MyRg1 
--name MyVm1
az vm stop 
--resource-group MyRg1 
--name MyVm1
az vm deallocate
 --resource-group MyRg1 
 --name MyVm1'
