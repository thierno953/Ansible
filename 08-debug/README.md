# Register, Debug and Shell in Ansible

* You can create variables from the output of an Ansible task with the task keyword register. You can use registered variables in any later tasks in your play.
* Debug: This module prints statements during execution and can be useful for debugging variables or expressions without necessarily halting the playbook. Useful for debugging together with the **when:** directive.

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
