## Deployment of Wordpress via Ansible on AWS Cloud

### This is Ansible playbook to install Wordpress on EC2 instance with RDP.
#### First at all to do this you must have some expiriense with AWS, to setup IAM, EC2->Key-pair, Security Groups, Network Interfaces etc.
#### After you clone repo, you will need to change ./vars/main-aws.yml and put your variables in that file. Start ansible script and wait until all steps are completed.  

##### Script that you need to run:
```
ansible-playbook playbook-ec2-wp-rds.yml 
```

#### Now you can open your Wordpress site http://PUBLIC_IP_EC2/wordpress.

#### To complete setup you must know DB Host (RDS), you can look it up at RDS->Endpoint (in newly created database).