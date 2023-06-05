APB Name
=========

A brief description of the APB goes here.

Playbook Bundle Structure
-------------------------

```
.travis.yml
Dockerfile
Makefile
README.md
apb.yml
defaults/
    main.yml
files/
handlers/
    main.yml
meta/
    main.yml
playbooks/
    deprovision.yml
    provision.yml
tasks/
    main.yml
templates/
tests/
    ansible.cfg
    inventory
    test.yml
vars/
    main.yml
```

Playbook Structure with inventories and vars on root
----------------------------------------------------

```
production                # inventory file for production servers
staging                   # inventory file for staging environment

group_vars/
   group1.yml             # here we assign variables to particular groups
   group2.yml
host_vars/
   hostname1.yml          # here we assign variables to particular systems
   hostname2.yml

library/                  # if any custom modules, put them here (optional)
module_utils/             # if any custom module_utils to support modules, put them here (optional)
filter_plugins/           # if any custom filter plugins, put them here (optional)

site.yml                  # main playbook
webservers.yml            # playbook for webserver tier
dbservers.yml             # playbook for dbserver tier
tasks/                    # task files included from playbooks
    webservers-extra.yml  # <-- avoids confusing playbook with task files
```

Playbook Structure with inventories and vars within environment
---------------------------------------------------------------

```
inventories/
   production/
      hosts               # inventory file for production servers
      group_vars/
         group1.yml       # here we assign variables to particular groups
         group2.yml
      host_vars/
         hostname1.yml    # here we assign variables to particular systems
         hostname2.yml

   staging/
      hosts               # inventory file for staging environment
      group_vars/
         group1.yml       # here we assign variables to particular groups
         group2.yml
      host_vars/
         stagehost1.yml   # here we assign variables to particular systems
         stagehost2.yml

library/
module_utils/
filter_plugins/

site.yml
webservers.yml
dbservers.yml

roles/
    common/
    webtier/
    monitoring/
    fooapp/
```

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

APB Variables
--------------

A description of the settable variables for this APB should go here, including any variables that are in defaults/main.yml, vars/main.yml, apb.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (i.e. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

A list of other APBs/roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your APB (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
