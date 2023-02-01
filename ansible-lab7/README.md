# Ansible Lab 7 - Let's create a Development/Production inventory file

We can have multiple inventory sets. Let's create a production and development inventory file and set a variable for them.

## Let's gather some ansible facts, these are dynamic variables automatically collected by ansible

1. Let's create an inventory directory.
2. Let's create an inventory file for development and production.
3. Let's set an environment variable and run the playbook.

```shell
ansible-playbook -i inventories/dev -K playbook1.yml
ansible-playbook -i inventories/prod -K playbook1.yml
```
