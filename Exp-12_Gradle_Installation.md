# Gradle Installation

1. Make sure the JAVA(JDK) version is installed first to suuport the installation of gradle.

```bash
sudo yum update -y
sudo yum install -y java-17-amazon-corretto-devel
sudo yum install java-1.8.0
```

```bash

#To check version of JAVA , use:
java -version
```

2. Then, install the Gradle from the link containing Gradle zip file and then, make a directory and unzip the file.

```bash
#Install the zip file.
sudo wget https://services.gradle.org/distributions/gradle-8.8-bin.zip
```

```bash
mkdir /opt/gradle
unzip -d /opt/gradle gradle-8.8-bin.zip
ls /opt/gradle/gradle-8.8
```

```text
The output is:
LICENSE  NOTICE  bin  getting-started.html  init.d  lib  media
```

3. Set the path of gradle in environment variables.

```bash
export PATH=$PATH:/opt/gradle/gradle-8.8/bin
```

4. Similarly, restart the AMI and then , check for the changes. If it still shows the gradle is not found. Then, use

```bash
sudo nano ~/.bash_profile
```

Then, add

```bash
# .bash_profile

# Get the aliases and functions
if [ -f ~/.bashrc ]; then
        . ~/.bashrc
fi

# User specific environment and startup programs

PATH=$PATH:$HOME/.local/bin:$HOME/bin
export PATH
export PATH=$PATH:/opt/gradle/gradle-8.8/bin

```

At last, check for the version:

```bash
gradle -v
```