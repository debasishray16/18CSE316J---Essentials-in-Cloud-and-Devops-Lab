# Ansible Installation

Step 1: Update the System
First, update your system's package index:

```bash
sudo yum update -y
```

Step 2: Install EPEL Repository
Ansible is available in the Extra Packages for Enterprise Linux (EPEL) repository. You need to install this repository first:

```bash
sudo amazon-linux-extras install epel -y
```

Step 3: Install Ansible
Now, you can install Ansible using yum:

```bash
sudo yum install ansible -y
```

Step 4: Verify the Installation
To verify that Ansible is installed correctly, check the version:

```bash
ansible --version
```
