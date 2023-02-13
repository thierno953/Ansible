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
- Security Compilance.
- Scripts (Time , Coding Skills, Maintenace).

# Ansible Architecture

### Ansible Use Case 1

```bash
-----------------------------------------------------------------------------
System Admin <---------->  Test Team <-----------> Delivery Team
-----------------------------------------------------------------------------
                             |
------------------------------------------------------------------------------
|                            |                                  |
Playbooks                Templates                          Modules
------------------------------------------------------------------------------
|           |           |            |              |         |         |
Create   Provision     Push      Configuration   Security  Services    Deploy
------------------------------------------------------------------------------
|           |           |            |               |                  |
Instances  Server    OS Image     Configured       Approved         App-ready
                                    Server         Server            Server
------------------------------------------------------------------------------
                      Pool of running servers
------------------------------------------------------------------------------
```

### Ansible Use Case 2

```bash
------------------------------------------------------------------------------
Ansible Management Node  <--------------------------------------->
       |                                        |
       |                          ------------------------------
<------------>                    | ssh         ssh         ssh  |
|             |                   ------------------------------
Playbook     Inventory             Node 1      Node 2       Node 3
------------------------------------------------------------------------------
```

## How to use these Labs ?

1. Install Ansible: https://docs.ansible.com/ansible/latest/installation_guide/installation_distros.html

2. Install Oracle Virtual Box: https://www.virtualbox.org/

3. Install Vagrant: https://developer.hashicorp.com/vagrant/downloads

4. Start the vagrant instance.

```shell
vagrant up
```

5. SSH into the <NAME> virtual machine.

```shell
vagrant ssh <NAME>
```