# Ansible Role Creation

To check the roles in Ansible directory.

```bash
cd /
cd etc
cd ansibleF
cd roles
ls -lS
```

or

```bash
cd / ; cd etc ; cd ansible ; cd roles
```

To create roles in Ansible directory, go to parent directory

```bash
cd ~
sudo ansible-galaxy init /etc/ansible/roles database_installation
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
