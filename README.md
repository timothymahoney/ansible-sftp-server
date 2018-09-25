# ansible-sftp-server
Simple SFTP Server setup

This playbook stands up a new EC2 server and provisions it to act as an SFTP server via Ansible.

Requires ansible and boto, generally stood up via virtualenv.

Install your aws credentials via export:

```
export AWS_ACCESS_KEY_ID=ABC123
export AWS_SECRET_ACCESS_KEY=XYZ123
```

Create an EC2 key pair and add it to your ssh-agent

ssh-add keypair.pem

Get your VPC ID and Subnet ID, export them for use by Ansible

```
export VPC_ID=vpc-abc123
export SUBNET_ID=subnet-xyz123
```

Run the ansible playbook

ansible-playbook -i ec2.py -u ubuntu -e vpc_id=${VPC_ID} -e subnet_id=${SUBNET_ID}