# Ansible Vault

- The **Vault** is a feature of Ansible that allows you to keep sensitive data such as passwords or keys protected at rest, rather than as plain text in playbooks or roles.

**Why use Ansible Vault ?**

- Ansible is used for automation, the playbooks contain certain credentials, **SSL certificates**, or other sensitive data. Usually, we store our sensitive data in the variable of vault.

**How Ansible Vault help us ?**

- It helps us to encrypt or decrypt sensitive variables that contain information and there are 2 ways to take care of sensitive data:

  - **1)** encrypt variables and embed them into the playbook.
  - **2)** encrypt the entire playbook.

  **Creating an Encrypted File**

  ```bash
  ansible-vault create example.yml
  ```

  **Encrypting Unencrypted Files**

  ```bash
  ansible-vault encrypt example.yml
  ```

  **Editing Encrypted Files**

  ```bash
  ansible-vault edit example.yml
  ```

  **Viewing Encrypted File**

  ```bash
  ansible-vault view example.yml
  ```

  **Decrypted Encrypted Files During Runtime**

  ```bash
  ansible-playbook -i hosts -K playbook1.yml --ask-vault-pass
  ```

  ```bash
  [control]
  ansible-control

  [webservers]
  node1
  ansible_ssh_host=192.168.56.101
  ansible_ssh_user=root
  ansible_ssh_pass=vagrant

  [webstack:children]
  webservers
  ```
