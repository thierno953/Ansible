# Ansible Lab 6 - Using Tags

Tags allow us to categorize items in our playbooks and tasks.

1. Let's use --list-tags to see currently enabled tags.
2. Let's start adding tags to our playbooks and tasks. Let's use the 'always' keyword for the common host file copy task
3. Let's use --list-tags again to see now enabled tags and see tag inheritance.
4. Let's run our playbooks using tags to run only certain items

## Let's check the current tags

```shell
ansible-playbook -i hosts -K playbook1.yml --list-tags
```

## Let's run playbook for specific tags

```shell
ansible-playbook -i hosts -K playbook1.yml --tags proxy
ansible-playbook -i hosts -K playbook1.yml --tags web
ansible-playbook -i hosts -K playbook1.yml --tags installation
ansible-playbook -i hosts -K playbook1.yml --tags configuration
ansible-playbook -i hosts -K playbook1.yml --tags web,configuration
ansible-playbook -i hosts -K playbook1.yml --tags nginx_configuration
```

