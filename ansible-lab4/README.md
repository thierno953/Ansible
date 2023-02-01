# Ansible Lab 5 - Roles and Ansible Galaxy

ansible-galaxy allows us to upload roles and also provides a great default framework to create your own roles.

## Role directory structure

- default: Contains default variables for the role. Variales in default have the lowest priority so they are easy to override.
----------
- vars: Contains variables for the role. Variables in vars have higher priority than variables in defaults directory.
-------
- tasks: Contains the main list of steps to be executed by the role.
--------
- files: Contains files which we want to be copied to the remote host. We don't need to specify a path of resources stored in this directory.
--------
- templates: Contains file template which supports modifications from the role.
---------
- meta: Contains metadata of role like an author, support platforms, dependencies.
-------
- handlers: Contains handlers which can be invoked by "notify" directives and are associated with service.
----------

## Let's modify the playbook so that it uses the role feature to configure apache2

1. Let's use ansible-galaxy to create a web server role scaffold
2. Let's move the tasks to the roles\webserver folder
3. Let's run the playbook

### Let's create an Apache2 role, move the tasks/handlers/templates to the new roles/apache2 structure. Let's run the playbook.

```shell
sudo apt-get install tree
```

```shell
ansible-galaxy init roles/apache2
ansible-playbook -i host -K playbook1.yml
```

### Let's create a 'common' role and add it to the 'web', 'loadbalancer' and 'database' servers

1. Let's use ansible-galaxy to create an common role scaffold
2. Let's configure the tasks/main.yml and the tasks/install_tools.yml
3. Let's run the playbook and test

```shell
ansible-galaxy init roles/common
ansible-playbook -i host -K playbook1.yml
```

### Let's create an nginx role and configure the configuration

1. Let's use ansible-galaxy to create an nginx role scaffold
2. Let's configure tasks, handlers and templates

```shell
ansible-galaxy init roles/nginx
ansible-playbook -i host -K playbook1.yml
```
