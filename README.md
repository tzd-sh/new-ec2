# new-ec2
Vagrant - Create a new AWS EC2 Instance (very quickly)

Pre-Requisites:

1. You should already have Vagrant installed in your environment

2. You should already have vagrant-aws plugin and a dummy box installed as per https://github.com/mitchellh/vagrant-aws/blob/master/README.md
```
$ vagrant plugin install vagrant-aws
$ vagrant box add dummy https://github.com/mitchellh/vagrant-aws/raw/master/dummy.box
```

3. Your shell should already have AWS CLI installed and configured (aws config) with access keys already saved into ~/.aws/credentials




## Begin User-Configurable Variables - change as necessary or as needed

VAGRANT_DIR=/path/to/your/vagrant/directory

## 'ami-8c1be5f6' is default Amazon Linux AMI for US East (N. Virginia); change as you wish
AMI="ami-8c1be5f6"

## Amazon Linux AMI has 'ec2-user' as the login name; Ubuntu AMI uses 'ubuntu' as the login name
SSH_USER="ec2-user"

INSTANCE_TYPE="t2.micro"
SECURITY_GROUPS="name_of_your_security_group_with_open_ssh_port"

KEYPAIR="aws_name_of_keypair"
SSH_PRIVATE_KEY="/path/to/your/.ssh/private_key.pem"

## End User-Configurable Variables
##################################
