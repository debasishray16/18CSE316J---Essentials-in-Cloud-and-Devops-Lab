# Ansible Role Creation

To check the roles in Ansible directory.

```bash
cd /
cd etc
cd ansible
cd roles
ls -lS
```

or

```bash
cd / ; cd etc ; cd ansible ; cd roles
```

To create roles in Ansible directory, go to parent directory

```bash
cd /etc/ansible/roles
sudo ansible-galaxy init database_installation
```

Now, then check the creation of roles.

```bash
cd / ; cd etc ; cd ansible ; cd roles
```

The file structure of "database_installation" roles

```text
[ec2-user@ip-172-31-33-7 database_installation]$ ls -lS
total 4
-rw-r--r--. 1 root root 1328 Jul  5 13:19 README.md
drwxr-xr-x. 2 root root   39 Jul  5 13:19 tests
drwxr-xr-x. 2 root root   22 Jul  5 13:19 defaults
drwxr-xr-x. 2 root root   22 Jul  5 13:19 handlers
drwxr-xr-x. 2 root root   22 Jul  5 13:19 meta
drwxr-xr-x. 2 root root   22 Jul  5 13:19 tasks
drwxr-xr-x. 2 root root   22 Jul  5 13:19 vars
drwxr-xr-x. 2 root root    6 Jul  5 13:19 files
drwxr-xr-x. 2 root root    6 Jul  5 13:19 templates
```

## To Create YAML file for installation of Git and checking all the updates in client.

1. Create a file in etc directory with name "Private Key" which stores all the private keys of client1:

```bash
cd /etc
mkdir private key
```

2. Copy the private key SHA from the saved file and store them accordingly in files.

```bash
sudo nano client1.pem
sudo nano client2.pem
```

**NOTE: Note the directory location.**

3. Then, navigate to file ansible and create hosts file ans type the command:

```bash
cd /etc/ansible
sudo nano hosts
```

```bash
# In hosts file:
# <ip_address> ansible_ssh_private_key_file=<location> ansible_ssh_user=ec2-user

[ansible_client]
172.13.23.2 ansible_user_private_key_file=/etc/private_keys/client1.pem ansible_ssh_user=ec2-user
```

4. Now , change the directory location to parent directory and create a YAML file:

```bash
sudo nano git_install.yml
```

```yaml
---
- name: Install Git
  hosts: ansible_client
  remote_user: host
  become: true
  tasks:
    - name: Ensure all packages are up to date
      yum:
        name: '*'
        state: latest

    - name: Install Git
      yum:
        name: git
        state: present

```

To run the YAML file, type: 

```bash
ansible-playbook git_install.yml --syntax-check
ansible-playbook git_install.yml
```