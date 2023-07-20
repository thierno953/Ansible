1. create the ansible machine sg

   ```jsx
    ssh from ip
   ```

2. create the server sg

   ```jsx
    ssh from ansible sg
    http from port 80
   ```

3. launch the ansible-machine

   ```jsx
    amazon linux 2
   ```

4. create key pairs on the ansible-machine

   ```jsx
    ssh-keygen -t rsa -b 2048
   ```

5. import public key into the ec2 console

   ```jsx
   ansible - pub - key;
   ```

6. launch the servers

   ```
    key pair: ansible-pub-key
    sg: server-sg
   ```

7. test connection

   ```
    ssh private ip
   ```

8. install ansible on ansible-machine

   ```
    sudo yum update -y
    sudo amazon-linux-extras install ansible2 -y
   ```

9. create inventory file

10. create playbook

```jsx
 ansible all --key-file ~/.ssh/id_rsa -i inventory -m ping -u ec2-user
```

11. creat ansible.cfg file

```jsx
 [defaults]
 remote_user = ec2-user
 inventory = inventory
 private_key_file = ~/.ssh/id_rsa
```

13. run the ansible playbook

```jsx
ansible - playbook[file];
```
