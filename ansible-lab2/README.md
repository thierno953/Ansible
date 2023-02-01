# Ansible Lab 2 - Playbooks and Templates

1. Let's create a playbook and review the YAML file details
2. Let's create templates
3. Let's run the playbook
4. Let's test connectivity to the server

### Let's run the playbook

```shell
ansible-playbook -i host -K playbook1.yml
```

### Let's test the connectivity to the server

```shell
curl web01:8000
curl web02:8000
```
