# Ansible Roles

- Ansible roles allow you to develop reusable automation components by grouping and encapsulating related automation artifacts, like configuration files, templates, tasks, and handlers.

# Roles Continued...

- A role directory structure contains directories: default, vars, tasks, files, templates, meta, handlers. Each directory must contain a main.yml file which contains relevant content. Let' look little close to each directory.

- **default:** contains default variables for the role. Variables in default have the lowest priority so they are easy to override.

- **vars:** contains variables for the role. Variables in vars have higher priority than variables in defaults directory.

- **tasks:** contains the main list of steps to be executed by the role.

- **files:** contains files which we want to be copied to the remote host. We don't need to specify a path of resources stored in this directory.

- **templates:** contains file template which supports modifications from the role. We use the <Jinja2 templating> language for creating templates.

- **meta:** contains metadata of role like an author, support platforms, dependencies.

- **handlers:** contains handlers which can be invoked by "notify" directives and are associated with service.

### Let's create an httpd role, move the tasks/handlers/templates to the new roles/httpd structure. Let's run the playbook.

```bash
sudo yum install tree

ansible-galaxy init roles/roleshttpd
```

## Using roles in playbook

```bash
---
- hosts: webservers
  become: yes
  roles:
    - roleshttpd
```

```bash
├── hosts
├── playbook1.yml
└── roles
    └── roleshttpd
        ├── defaults
        │   └── main.yml
        ├── files
        ├── handlers
        │   └── main.yml
        ├── meta
        │   └── main.yml
        ├── README.md
        ├── tasks
        │   ├── install.yml
        │   ├── main.yml
        │   └── user.yml
        ├── templates
        ├── tests
        │   ├── inventory
        │   └── test.yml
        └── vars
            └── main.yml
```
