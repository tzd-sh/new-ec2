# new-ec2
NEW-EC2: Vagrant create a new AWS EC2 Instance (very quickly)

Written by: Zheng-Da Tan

Acknowledgement: This is pretty much an automation of the information provided from the official Vagrant-AWS plugin at https://github.com/mitchellh/vagrant-aws

Pre-Requisites:

1. You should already have Vagrant and Python installed in your environment

2. You should already have vagrant-aws plugin and a dummy box installed as per https://github.com/mitchellh/vagrant-aws/blob/master/README.md
```
$ vagrant plugin install vagrant-aws
$ vagrant box add dummy https://github.com/mitchellh/vagrant-aws/raw/master/dummy.box
```

3. You should already have a set of access keys created in AWS IAM with permission to administer EC2.  Your shell should already have AWS CLI installed and configured with the access keys already saved into ~/.aws/credentials
```
$ pip install awscli
$ aws configure
```

These are the variables you should edit in the script before running:

This is the directory where you want your vagrant instances to be created under:
```
VAGRANT_DIR=/path/to/your/vagrant/directory
```
'ami-8c1be5f6' is default Amazon Linux AMI for US East (N. Virginia); change as you wish:
```
AMI="ami-8c1be5f6"
```
Amazon Linux AMI has 'ec2-user' as the login name; Ubuntu AMI uses 'ubuntu' as the login name:
```
SSH_USER="ec2-user"
```
This is the AWS instance type that the EC2 instance will be started as:
```
INSTANCE_TYPE="t2.micro"
```
You should create a Security Group in AWS Console with Port 22 and any additional ports you require open to access from your computer, and use the Group ID below:
```
SECURITY_GROUP_ID="sg-XXXXXXXX"
```
This is the Subnet ID of your VPC:
```
SUBNET_ID="subnet-XXXXXXXX"
```
This is the "Key pair name" in AWS EC2 Console:
```
KEYPAIR="aws_name_of_keypair"
```
This is the path to the private key that you have downloaded when you initially created the AWS Key Pair:
```
SSH_PRIVATE_KEY="/path/to/your/.ssh/private_key.pem"
```
