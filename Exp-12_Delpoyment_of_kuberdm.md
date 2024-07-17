# Kubernetes Deployment

```bash
sudo yum update -y

sudo yum install -y ca-certificates curl gnupg2

sudo mkdir -p /etc/pki/rpm-gpg

curl -fsSL https://pkgs.k8s.io/core:/stable:/v1.30/deb/Release.key | sudo tee /etc/pki/rpm-gpg/kubernetes-gpg-key

sudo rpm --import /etc/pki/rpm-gpg/kubernetes-gpg-key

sudo tee /etc/yum.repos.d/kubernetes.repo <<EOF
[kubernetes]
name=Kubernetes
baseurl=https://pkgs.k8s.io/core:/stable:/v1.30/rpm/
enabled=1
gpgcheck=1
gpgkey=file:///etc/pki/rpm-gpg/kubernetes-gpg-key
EOF

sudo chmod 644 /etc/yum.repos.d/kubernetes.repo
sudo yum update -y

sudo yum install -y kubectl
```