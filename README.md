ansible-role-dploy-docker-swarm-stack
=========

This role deploys one or more Docker Swarm Stack from compose file and env variables using a Docker Swarm manager node with ssh.

You can use docker-compose.yml files as is, or use docker-compose.yml.j2 files as jinja2 templates for generating final docker-compose.yml file. This will be autodetected at runtime (by existence).

TODO
----

Unneeded stacks are not removed by this role. They have to be removed manually on the Swarm Manager node by running:
    
    docker stack rm STACKNAME

Requirements
------------

Ansible 2.3

Role Variables
--------------

See defaults/main.yml for variables.

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

After setting the variables (see defaults/main.yml) you can use something like:

    - hosts: swarm-manager-nodes[0]
      roles:
         - { role: ansible-role-deploy-docker-swarm-stack, deploy_stack_postfix: "-prod" }

You can deploy one stack with role parameters:

    - hosts: swarm-manager-nodes[0]
      roles:
         - { role: ansible-role-deploy-docker-swarm-stack, stack: {name: xyz123} }

License
-------

BSD

Author Information
------------------

DBLaci
