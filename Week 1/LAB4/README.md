# Lab 4: Create and use an SSH public-private key pair for Linux VMs in Azure

1. Supported SSH key formats
2. Create an SSH key pair
3. Provide an SSH public key when deploying a VM
4. SSH into your VM

### Notes:

Quickstart: SSH for Linux VMs
* https://docs.microsoft.com/en-us/azure/virtual-machines/linux/mac-create-ssh-keys

Quickstart for Bash in Azure Cloud Shell
* https://docs.microsoft.com/en-us/azure/cloud-shell/quickstart



### Procedures
SSH-2 (SSH protocol 2)
RSA public private key

Create ssh keys
'az sshkey create --name ssh1 --resource-group rg2 --location eastus'
results:
Private key is saved to "C:\Users\DELL\.ssh\1638475279_004805".
Public key is saved to "C:\Users\DELL\.ssh\1638475279_004805.pub".
	
Provide an SSH public key when deploying a VM
to do this the public key was first looked up by using this command
'cat ~/.ssh/id_rsa.pub 
result:
AAAAB3NzaC1yc2EAAAADAQABAAABAQC9VA2/+7ebWm9cgFjQ6787z6RKb2ba9w0jMDFr9Okf9AHoZ9DvzTCiUrHDYZMg444dcNS6AQ3wFCVq4Fwllg5UFPm1bcnAVdX1ZlOJEKLIxgTInFqfbhayAML+nzlSBiUSTusZZ3K+hjsOiriYUgNQnThEwBppm41SgE8kYmxwYnOcVKn34+rcIl5uOyqdCpSBx7OeSEabziqTHyD+uF/8ur1P/x/5Xn7u3pTuKkw0WjYywY3gGWxqV2fg1Ubt4fGJa255R0azX9l6f8ypiIAH8oSM8jrSCtBbfron2frC/CdyAk5+cQAR8L2T7livWjh6IOIeq5j1ZImIGw/ECnqB
so with this public key now i can create and deploy my vm 

