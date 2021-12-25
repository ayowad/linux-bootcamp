# Lab 1: Create a Linux virtual machine with the AWS CLI

1. Launch AWS Cloud Shell
3. Create virtual machine
4. Open port 80 for web traffic
5. Connect to virtual machine
6. Install web server
7. View the web server in action

### Notes:

Quickstart: Create a Linux VM
* https://aws.amazon.com/getting-started/launch-a-virtual-machine-B-0/

Quickstart for AWS CloudShell
* https://docs.aws.amazon.com/cloudshell/latest/userguide/working-with-cloudshell.html

# Launched the AWS instance

# Visit the AWS console and launched the aws web powershell
# Ran the following command to create an instance
aws ec2 run-instances --image-id ami-002068ed284fb165b --instance-type t2.micro --key-name wad_key

# Ran the below command to ensure my key is not publicly viewable
chmod 400 wad_key.pem

# Connected the instance
ssh -i "wad_key.pem" ec2-user@ec2-18-118-27-132.us-east-2.compute.amazonaws.com

# installed web server

# The super user command is required to install the web server

sudo su
yum update -y
yum install -y httpd

# Viewed web server in action
