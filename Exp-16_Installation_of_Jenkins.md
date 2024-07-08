# Jenkins Installation

```bash

sudo yum update -y
sudo yum install -y libXScrnSaver
sudo wget https://dl.google.com/linux/direct/google-chrome-stable_current_x86_64.rpm
sudo yum localinstall google-chrome-stable_current_x86_64.rpm -y
google-chrome --version

# This will display the Google Chrome version, confirming that it has been successfully installed on your EC2 instance.
```

```bash
sudo yum install -y wget unzip
sudo wget https://chromedriver.storage.googleapis.com/98.0.4758.102/chromedriver_linux64.zip
unzip chromedriver_linux64.zip
sudo mv chromedriver /usr/bin/chromedriver
chromedriver --version

# This will display the ChromeDriver version, confirming that it has been successfully installed on your EC2 instance.

```

```bash
sudo yum update -y
sudo yum search openjdk
sudo yum install -y java-11-amazon-corretto-devel
java -version

# This will display the installed Java version, confirming that OpenJDK 11 has been successfully installed on your EC2 instance.
```

```bash
sudo mkdir -p /usr/share/keyrings
sudo wget -O /usr/share/keyrings/jenkins-keyring.asc https://pkg.jenkins.io/redhat-stable/jenkins.io.key
sudo wget -O /etc/yum.repos.d/jenkins.repo https://pkg.jenkins.io/redhat-stable/jenkins.repo
sudo rpm --import /usr/share/keyrings/jenkins-keyring.asc
sudo yum update -y
sudo yum install -y jenkins
sudo systemctl start jenkins
sudo systemctl enable jenkins
```

To check the status of the Jenkins:

```bash
sudo systemctl status jenkins
```

To see the administrative password, type:

```bash
sudo cat /var/lib/jenkins/secrets/initialAdminPassword
```

Then, go to Security groups in EC2 instance and add an imbound rule with Custom TCP along with 8080 and CIDR values as "0.0.0.0/0".
Click on OK.

Then type your http://<your_public_ip>:8080 and access to Jenkins website view.
The, use the administrative password and login to it and then, create a new user and password and then start using the Jenkins to automate the job.
