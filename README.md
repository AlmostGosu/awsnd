# AWS Node Deployer
I built these playbooks becuase I suck with Cloudformation templates and needed something to build and tear down AWS environments, dynamically update inventory files, and basically manage my AWS Ansible playground. 

## The Setup
readthedocs: https://aws.amazon.com/blogs/apn/getting-started-with-ansible-and-dynamic-amazon-ec2-inventory-management/

Variables are set within the context of each role, because the roles are maintained independtly on Galaxy.

## Building
Network and host profiles to be deployed are in the `awsnd-deployer\tasks\hosts` & `awsnd-purger\tasks\security-groups` folders. Simply run `ansible-playbook -v -i inventory-ec2 test-deploy.yml` to test a deployment with default hosts & security groups.

## Cleaning up
The cleanup only relies on a couple variables set in the `awsnd-purger\vars\vars.yml` file and will discover the rest of your `awsnd_guid` tagged infrastructure and destroy it systematically. 
