# What is Ansible ?

- Ansible is very simple, open source and human readable automation tool.
  It is agentless and uses SSH connection to orchestrate all the tasks which we were talking above
  such as configuration management, application,
  and provisioning in a flat or multi-tier environment.

# Why Ansible?

- Provisioning.
- Configuration Management.
- Continuous Delivery.
- Application Deployment.
- Security Compliance.
- Scripts (Time , Coding Skills, Maintenace).

# YAML

- YAML is one of the most popular data "serialization" languages.
- It is human-readable and simple to understand for writing configuration files.
- YAML files either have the extension .yaml or .yml
- YAML stands for <YAML Ain't Markup Language.>

# Indentation

- A YAML file relies on whitespace and indenttaion to indicate nesting. only spaces can be used for indentation in YAML files. The number of spaces used for indentation doesn't matter as long as they are consistent.

```bsah
node:   #nesting level 1
  - yaml:  #nesting level 2 (2  spaces used for indentation)
      name: "YAML Ain't Markup Language" #string [literal] #nesting level 3
      type: awesome #string [literal]
      born: 2003 #number [literal]
```

# Mapping

- Mappings are used to associate key/value pairs that are unordered.

```bsah
name: "YAML Ain't Markup Language" #mapping
type: awesome
born: 2003
```

# Sequences

- Sequences in YAML are represented by using the hyphen (-) and space. They are ordered and can be embedded inside a map using indentation.

```bsah
languages:
#Sequences
  - YAML
  - JAVA
  - XML
  - Python
  - C
```

# Comment in YAML

- YAML file also supports comments, unlike JSON. A comment starts with #.

```bsah
---
#Comments inside a YAML file can be added followed by the '#' character

company: spacelift
```

# Inventory

- An Ansible inventory is a collection of managed hosts we want to manage with Ansible for various automation and configuration management tasks. Typically, when starting with Ansible, we define a static list of hosts known as the inventory.
- By default, the inventory is stored in /etc/ansible/hosts, but you can specify a different location with the -i flag or the <ansible.cfg> configuration file.

```bsah
[control]
ansible-control

[webservers]
node1
node2

[databases]
db01
db02

[webstack:children]
webservers
databases
```

```bash
---
- hosts: webservers
  become: yes
  tasks:
    - name: install java
      yum:
        name: java
        state: latest
    - name: install jenkins
      yum:
        name: jenkins
        state: latest
```

# Ansible Lab 1 - Installation and Inventory file

### Setup Vagrant and connect to ansible-control server

```shell
 vagrant up
 vagrant ssh ansible-control
```

### Copy hosts file on ansible-control

```shell
cp /vagrant/hosts_file /etc/hosts
```

### Install Ansible

```shell
 sudo yum install ansible -y
```

### Create a SSH key and copy to all servers

```shell
ssh-keygen -t ed25519 -C "Ansible Key Pair"
cd ~/.ssh/
cat ~/.ssh/id_ed25519.pub
ssh-copy-id localhost
ssh-copy-id node1
```

### Run a ad-hoc command to the webstack group

```shell
ansible webstack -i hosts -m command -a hostname
ansible webstack -i hosts -m command -a date
```

### Run playbook

```shell
ansible-playbook -i hosts -K playbook1.yml
```

## How to use these Labs ?

1. Install Ansible: https://docs.ansible.com/ansible/latest/installation_guide/installation_distros.html

2. Install Oracle Virtual Box: https://www.virtualbox.org/

3. Install Vagrant: https://developer.hashicorp.com/vagrant/downloads

4. Start the vagrant instance.

```shell
vagrant validate

vagrant up
```

5. SSH into the <NAME> virtual machine.

```shell
vagrant ssh <NAME>
```
