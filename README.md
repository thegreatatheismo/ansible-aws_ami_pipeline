aws-custom_ami_pipeline
=========

An Ansible role to create a custom, hardened, ami from the RHEL8 marketplace image.

Requirements
------------

- AWS Account with key-pair
- AWS Dynamic Inventory
- SCAP Work Bench (if customising the hardening playbook)

Role Variables
--------------

- **access_key_tower** - Tower environment variable for AWS credentials.
- **secret_key_tower** - Tower environment variable for AWS credentials.
- **security_token_tower** - Tower environment variable for AWS credentials.
- **access_key** - AWS credentials (store these in a vault).
- **secret_key** - AWS credentials (store these in a vault).
- **security_token** - AWS credentials (store these in a vault).
- **ami_id** - RHEL8 Marketplace AMI ID.
- **region** - AWS region.
- **sec_group** - AWS security group to add instance to.
- **subnet_id** - AWS subnet to deploy instance in.
- **instance_type** - Instance flavour.
- **key** - Name of pre-existing AWS key-pair to use.
- **id** - Version number for idempotence.
- **tag** - Tag for instance - required for finding instance_id in several plays.
- **ami_name** - Name of the AMI. Make this meaningful.


Dependencies
------------

- AWS Dynamic Inventory

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: ec2
      roles:
         - aws-custom_ami_pipeline

License
-------

BSD

Author Information
------------------

Stephen Leahy
sleahy@redhat.com