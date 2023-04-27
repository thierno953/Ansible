# Register, Debug and Shell in Ansible

- You can create variables from the output of an Ansible task with the task keyword register. You can use registered variables in any later tasks in your play.
- Debug: This module prints statements during execution and can be useful for debugging variables or expressions without necessarily halting the playbook. Useful for debugging together with the **when:** directive.
- Ansible shell module is designed to execute Shell commands against the target Unix based hosts. Unlike the Ansible command module, Ansible Shell would accept any highly complexed commands with pipes, redirection etc and you can also execute Shell scripts using Ansible Shell module.

```bash
---
- hosts: webservers
  become: yes
  tasks:
    - name: register date and check
      shell: |
        date
        ifconfig
        uptime
        hostname

      register: out

    - name: debug messages
      debug:
        var: out
```
