# Ansible Lab 1 - Installation and Inventory file basics

### Setup Vagrant and connect to ansible-control server

```shell
vagrant validate
vagrant up
vagrant ssh ansible-control
```

### Copy hosts file on ansible-control

```shell
sudo cp /vagrant/hosts_file /etc/hosts
```

### Install Ansible

```shell
sudo apt-get install ansible
```

### Create a SSH key and copy to all servers

```shell
ssh-keygen -t ed25519 -C "Ansible Key Pair"
ssh-copy-id localhost
ssh-copy-id web01 && ssh-copy-id web02 && ssh-copy-id loadbalancer && ssh-copy-id db01
```

### Run a ad-hoc command to the webstack group

```shell
ansible webstack -i hosts -m command -a hostname
ansible webstack -i hosts -m command -a date
```

### Install python-simplejson

```shell
ansible all -i hosts -m command -a 'sudo apt-get -y install python3'
```
