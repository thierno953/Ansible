# Ansible Vault

- The **Vault** is a feature of Ansible that allows you to keep sensitive data such as passwords or keys protected at rest, rather than as plain text in playbooks or roles.

## Why use Ansible Vault ?

- Ansible is used for automation, the playbooks contain certain credentials, SSL certificates, or other sensitive data. Usually, we store our sensitive data in the variable of vault.

```bash
[control]
ansible-control

[webservers]
node1

[webstack:children]
webservers
```
