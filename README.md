<h2> Setting up environment </h2>

Ansible uses Boto for AWS interactions, so you'll need that installed on your control host. I also used AWS CLI tools, so get those too.

<i> pip install python-boto awscli </i>

I worked on Ubuntu. So, to install Ansible:

<i> add-apt-repository ppa:ansible/ansible
apt-get install ansible </i>

Now, there is one credentials.yml file where all the AWS related environment varaibles can be defined:

aws_access_key: YOUR_ACCESS_KEY
aws_secret_key: YOUR_SECRET_KEY
region: us-east-1
  #MAKE SURE THAT SecG AND SubG both are in same VPC
  #PORT 22 has to be open for SSH
subnet_group: SUBNET_ID
security_group: SECURITY_GROUP_ID

Apart from this, you will need to setup a SSH key.

<i> ssh-keygen </i>

And then copy the public key in the same directory (where Playbooks are cloned). This key is used to SSH to the new spawn instance.


NOTE: Ubuntu 16.04 comes with Python3, whereas Ansible expects Python2 version. That's why, Python-2 was installed as the first task on remote machine.
