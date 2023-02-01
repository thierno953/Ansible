# What is Ansible ?

- Ansible is very simple, open source and human readable automation tool.
It is agentless and uses SSH connection to orchestrate all the tasks which we were talking above
such as configuration management, application,
and provisioning in a flat or multi-tier environment.

- Ansible Architecture

```shell
Ansible Server <-------------------------------->
       |                                        |
       |                          ------------------------------
<------------->                   | ssh         ssh         ssh|
|             |                   ------------------------------
Playbook     Inventory             Node 1      Node 2       Node 3
```
# Features of Ansible
- Easy setup
- Agentless
- Python as a backend
- Simple and human readable

# Ansible Labs

## How to use these Labs

1. Install Oracle Virtual Box: https://www.virtualbox.org/

2. Install Vagrant: https://developer.hashicorp.com/vagrant/downloads

3. Start the vagrant instance.

```shell
vagrant up
```

4. SSH into the ansible-control virtual machine.

```shell
vagrant ssh ansible-control
```
