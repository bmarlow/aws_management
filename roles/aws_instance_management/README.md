aws_instance_management
=========

This role can be invoked to the do the following:
1.  Tag instances that are missing the 'AlwaysUp' tag
2.  Shutdown instances that don't have the AlwaysUp:True tag
3.  Remove/delete instances that have been shutdown more than 30 days

Requirements
------------

Ansible.  Internet.  AWS

Role Variables
--------------

This role requires a few variable to run correctly.
aws_access_key: your aws access key
aws_secret_key: your aws secret key
aws_regions: a list of regions to query
one of the following must be set to True (if you want to actually do anything)
set_tags: assign tags to instances missing them
nightly_shutdown: shutdown instances that don't have the tag AlwaysUp:True
shutdown_over_thirty: nuke/terminate instances that have been shutdown over 30 days

Dependencies
------------

Appropriate AWS credentials


Example Playbook
----------------

ansible-playbook -i localhost, run.yml -e "@vars.yml"
(where vars.yml contains the required vars)

or
ansible-playbook -i localhost, run.yml aws_instance_management
(if you have decided to shove your vars in the vars.yml file within the role)

License
-------

BSD

Author Information
------------------

Brandon Marlow lives in the Pacific Northwest with his wife and a gaggle of animals.  In his (little) spare time he enjoys building things and writing terrible json queries.
