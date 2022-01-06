# Lab 4: Manage Packages and Services on a Linux VM (Azure or AWS)

1. Create a Linux VM
2. Install the Apache Web Server
3. Start the service status via command line
4. Investigate the service status via command line
5. Stop the service 

Challenge: Create a boostrapping script that will install and start this service on new EC2 VMs

### Notes:

Install and Configure Apache (Ubuntu)
* https://ubuntu.com/tutorials/install-and-configure-apache#1-overview

How to install Apache on RHEL 8 / CentOS 8 Linux
* https://linuxconfig.org/installing-apache-on-linux-redhat-8

How to use cloud-init to customize a Linux virtual machine in Azure on first boot
* https://docs.microsoft.com/en-us/azure/virtual-machines/linux/tutorial-automate-vm-deployment

Create bootstrap actions to install additional software
* https://docs.aws.amazon.com/emr/latest/ManagementGuide/emr-plan-bootstrap.html

# Used the aws GUI to create a virtual machine named: apache_web_server
# installed the apache web server (httpd)

# started the service with the AWS CLI

sudo su
yum update -y
yum install httpd -y


# Queried system status
systemctl status

![image](https://user-images.githubusercontent.com/94347897/148458829-dd69f5f0-8c6e-4332-91d2-61a303e6a4c3.png)
