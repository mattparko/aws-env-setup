## AWS environment setup
Some basic building blocks for setting up demo environments in AWS using Ansible

### Prereqs
1. An AWS environment (the "AWS Blank Open Environment" in RHDP is perfect)
2. Export the following environment variables (add your credentials and update region as needed)
    ```
    export AWS_ACCESS_KEY_ID=my_access_key_id
    export AWS_SECRET_ACCESS_KEY=my_secret_access_key
    export AWS_REGION=ap-southeast-2
    ```
3. Install Ansible dependencies on control node
   - ansible-core (tested on 2.16)
   - python3-boto
   - python3-boto3
   - python3-passlib
4. Install Ansible collections
   ```
   ansible-galaxy install -r requirements.yml
   ```
5. Ensure you have a public ssh key located at `~/.ssh/id_rsa.pub`

### Managing EC2 instances
1. Start all: `ansible-playbook manage_ec2_instances.yml -e action=start`
2. Stop all: `ansible-playbook manage_ec2_instances.yml -e action=stop`
3. Delete all: `ansible-playbook manage_ec2_instances.yml -e action=delete`

### Notes
1. These playbooks can be run multiple times
2. __Be careful with your password and secrets management!__

