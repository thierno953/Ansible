# Ansible 6 Lab - Ansible Variables

Two types of variables. Set of users and "ansibles facts".

## Let's gather some ansible facts, these are dynamic variables automatically collected by ansible

1. Let's use the configuration module to gather information about a system.
2. Let's display the output and discover any useful information
3. Let's use {{ ansible_facts['nodename'] }} for the localhost nodename variable. Let's add this to the index.html file.
4. Let's use a loop to dynamically access the node name of both web servers. let's add this to the mysite configuration of the nginx proxy server.

```shell
ansible -i hosts proxy -m setup

ansible -i hosts proxy -m setup >> ansible_facts.json
```

```shell
{{ ansible_facts['nodename'] }}

{% for host in groups['webservers'] %}
        server {{ hostvars[host]['ansible_facts']['nodename'] }}:8000;
{% endfor %}
```

```shell
ansible-playbook -i hosts -K playbook1.yml --tags configuration
ansible-playbook -i hosts -K playbook1.yml
ssh loadbalancer
cat /etc/nginx/sites-enabled/mysite
```

## Let's move the user-defined variables to another location

1. Let's move our current variables into the group_vars/all variables
2. Let's add these variables to our mysite nginx configuration
3. Let's create the host_vars folder and create a unique variable for web01
