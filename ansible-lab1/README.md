# Ansible Lab 1 - Installation and Inventory File Basics

### Let's configure Vagrant and connect to the ansible-control server

``` shell
wanderer validate
vagabond
vagrant ssh ansible control
```

### Copy the hosts file to ansible-control

``` shell
sudo cp /vagrant/hosts_file /etc/hosts
```

### Install Ansible

``` shell
sudo apt-get install ansible
```

### Let's create an SSH key and copy it to all servers

``` shell
ssh-keygen -t ed25519 -C "Ansible key pair"
ssh-copy-id localhost
ssh-copy-id web01 && ssh-copy-id web02 && ssh-copy-id loadbalancer && ssh-copy-id db01
```

### Let's run an ad-hoc command to the webstack group

``` shell
ansible webstack -i hosts -m command -a hostname
ansible webstack -i hosts -m command -a date
```

### Let's install python-simplejson

``` shell
ansible all -i hosts -m command -a 'sudo apt-get -y install python-simplejson'
```