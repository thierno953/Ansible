# Ansible CLI - free version

* Installation
* Modules
* Playbooks
* Roles
* Vault

```bash
Ansible-galaxy   #used to work the roles
Ansible-tower    #gui mode (chargable)
Ansible-doc      #gives documents
Ansible-vault    #storage used encript/decript the files
```

```bash
sudo yum search python
sudo yum install python3-pip.noarch -y
python --version
pip3 --version
pip3 install ansible --user
ansible --version
```

```bash
[prodappserver]
192.168.56.100 controller
192.168.56.101 server1

[dbservers]
192.168.56.102 server2
```

```jsx
nano /etc/hosts  #hosts -- give the info of other machines
```
**Ansible Modules:** One time executable command

```bash
#1. ping        //If host file /etc/ansible hosts
ansible all -m ping               
ansible prodappserver -m ping
ansible dbservers -m ping
ansible -i hosts all -m ping        #(/home/vagrant)
ansible -i /etc/hosts all -m ping   #(/etc/hosts)
ansible -i /etc/hosts all -m setup

#2. setup      
ansible all -m setup  #Give full information of all machines
ansible all -m setup -a "filter=ansible_distribution"  #(ansible_distribution of all machines)

#3. shell      //Execute the shell commands in the remote machines
ansible all -m shell -a "pwd"
ansible all -m shell -a "ls -la"
ansible all -m shell -a "date"
ansible all -m shell -a "touch abc.txt" -b

ansible -i /etc/hosts all -m shell -a "date"
ansible -i /etc/hosts all -m shell -a "ls /"
ansible -i /etc/hosts all -m shell -a "ls -la"
ansible -i /etc/hosts all -m shell -a "pwd"
ansible -i /etc/hosts all -m shell -a "touch /opt/file.txt" -b
ansible -i /etc/hosts all -m shell -a "ls /opt"


#4. yum/apt    //To install the package
# yum - state values: absent, installed, latest, present, removed
# apt - state values: absent, build-dep, fixed, latest, present
ansible -i /etc/hosts all -m yum -a "pkg=httpd state=installed"
ansible -i /etc/hosts all -m yum -a "pkg=httpd state=installed" -b
ansible -i /etc/hosts dbservers -m shell -a "apt update" -b
ansible -i /etc/hosts dbservers -m apt -a "pkg=apache2 state=latest" -b

ansible all -m yum -a "pkg=httpd state=installed" -b
ansible all -m apt -a "pkg=nginx state=latest" -b

#5. service    //To start/stop/restart the service
# linux:  state: reloaded, restarted, started, stopped
ansible -i prodappserver -m service -a "name=httpd state=started" -b
ansible -i prodappserver -m service -a "name=httpd state=stopped" -b

ansible all -m service -a "name=httpd state=started" -b
ansible all -m service -a "name=apache2 state=started" -b

#6. file/folder     //To create file or folder in the remote machines
ansible all -m file -a "path=/home/vagrant/abc.txt state=touch"        #new file
ansible all -m file -a "path=/home/vagrant/abc.txt state=file"         #existing file
ansible all -m file -a "path=/home/vagrant/folder state=directory"     #new directory
ansible all -m file -a "path=/home/vagrant/abc.txt state=file mode=0777 owner=root" -b  #permission existing file

#7. copy           // Copy files from source machine to remote machine
ansible prodappserver -m copy -a "src=/home/vagrant/index.html dest=/var/www/html/" -b

#8. command        // To execute the commands
ansible all -m command -a "sh /home/vagrant/script.sh" -b
ansible all -m command -a "date" -b
ansible all -m command -a "pwd" -b

#9. raw           // To give the output
ansible all -m raw -a "ls -la > temp.txt " -b
ansible all -m raw -a "ls -la /var/logs >> /home/vagrant/temp.txt " -b
``` 

**section in playbooks:** Multiple commands in the playbooks

```bash
1 - target section         #host information

2 - variable section       #variables information ex; packages names

3 - tasks section          #installed/ removed

4 - handler section        #deployment
```
