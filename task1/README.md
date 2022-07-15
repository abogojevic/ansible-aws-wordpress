## Deployment of Wordpress via Ansible on AWS Cloud

### This is Ansible playbook to install Wordpress on EC2 instance with RDP.
#### First at all to do this you must have some expiriense with AWS, to setup IAM, EC2->Key-pair, Security Groups, Network Interfaces etc.

#### First playbook named playbook-ec2-rds.yml installing EC2 Instance and RDS. In folder ./vars/main-aws.yml you must set some variables.

```
ansible-playbook -u ubuntu playbook-ec2-rds.yml 
```

#### This is not totaly automatic, need some changes, but that will be in next version :) When first playbook finish the job, you must use `Public IPv4 address` from EC2 Instances and put it in ./host-vars/aws-ec2.yml and also in ./hosts-aws Also like in first playbook must set some variables in ./vars/main-aws.yml for Wordpress.

#### Start playbook-wordpress.yml and wait till the end. After that you can open your site http://PUBLIC_IP_EC2/wordpress

```
ansible-playbook -i hosts-aws -u ubuntu playbook-wordpress.yml 
```

#### To complete setup you must know DB Host (RDS), if you dont know, you can look up in RDS->Endpoint.
