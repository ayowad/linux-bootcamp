# Lab 3: Manage Azure disks with the Azure CLI

1. Default Azure disks
2. Azure data disks
3. VM disk types
4. Launch Azure Cloud Shell
5. Create and attach disks
6. Prepare data disks
7. Take a disk snapshot

### Notes:

Quickstart: Manage Azure disks
* https://docs.microsoft.com/en-us/azure/virtual-machines/linux/tutorial-manage-disks

Quickstart for Bash in Azure Cloud Shell
* https://docs.microsoft.com/en-us/azure/cloud-shell/quickstart


# Notes:

Quickstart: Manage Azure disks
* https://docs.microsoft.com/en-us/azure/virtual-machines/linux/tutorial-manage-disks

Quickstart for Bash in Azure Cloud Shell
* https://docs.microsoft.com/en-us/azure/cloud-shell/quickstart

#Procedures:
By default two Azure disk is created with every virtual machine creation. Operating System Disk and Temporary Disk
to manage the Azure data disk, I created an Azure resource group
'az group create --name myrgDisk --location eastus'
and created a virtual machine
'az vm create \
  --resource-group myrgDisk \
  --name myvmDisk \
  --image UbuntuLTS \
  --size Standard_DS2_v2 \
  --admin-username azureuser \
  --generate-ssh-keys \
  --data-disk-sizes-gb 128'
but it returned an error stating that I do not have such privilege

I also created and attach disk to an existing virtual machine
'az vm disk attach \
    --resource-group myrgDisk \
    --vm-name myvmDISK \
    --name mydataDisk \
    --size-gb 128 \
    --sku Premium_LRS \
    --new'
I prepared data disk by first connecting to the already created vm
'ssh azureuser@(created ip used)'
after which the the superuser command was used to partition the disk
'sudo parted /dev/sdc --script mklabel gpt mkpart xfspart xfs 0% 100%'
but an error message was returned stating that /dev/sdc could not be found


