# Installation of Docker

```bash
sudo yum update -y
```

```bash
sudo yum install -y docker
sudo service docker start
sudo chkconfig docker on

sudo usermod -aG docker $USER
docker --version
sudo systemctl enable docker
```
