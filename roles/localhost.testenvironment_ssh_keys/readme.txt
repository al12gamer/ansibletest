This is the role that SHOULD, in theory, retrieve ssh keys for all local virtualized instances that are on the same network.
#again, these are files that were copied and Modified, originally from bonovoxly who used a BSD license
- This is quotation from https://github.com/bonovoxly/playbook/tree/master/roles/localhost.aws_ssh_keys: -
Retreives the SSH keys for all instances and adds them to the localhost's ~/.ssh/known_hosts file. Does the following:

Removes all commented ~/.ssh/known_hosts entries with # {{ marker_vars|default(vpc.resource_tags.Organization) }}
Gets the SSH fingerprints for all instances using aws ec2 get-console-output.
Imports the private and public IP address and fingerpints for those instances into ~/.ssh/known_hosts.

Requirements
Boto and any software required to run Ansible AWS cloud modules. Uses the AWS CLI.

Role Variables
vpc
The vpc dictionary.
ec2_facts
From the role aws.ec2_facts.
An optional marker_vars variable.

Dependencies
aws.ec2_facts >> this will be known as testenvironment.box_facts

- end quotation - 

