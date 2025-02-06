# GitLab-installation-on-Ubuntu-22.0.4
Update Repository
```
sudo apt update
```
Install Prerequisites
```
sudo apt-get install -y curl openssh-server ca-certificates tzdata perl
```
Install Mail Server
```
sudo apt-get install -y postfix
```
Download and Execute Installation Script
```
curl https://packages.gitlab.com/install/repositories/gitlab/gitlab-ee/script.deb.sh | sudo bash
```
Installing with LetsEncrypt
```
sudo EXTERNAL_URL="https://git.nullstack.com" apt-get install gitlab-ee
```
Update the configuration file to not setup LetsEncrypt
```
sudo sed -i 's/^# letsencrypt\['\''enable'\''\] = nil$/letsencrypt["enable"] = false/' /etc/gitlab/gitlab.rb
```
Reconfigure the Application
```
sudo gitlab-ctl reconfigure
```
Restart the Application
```
sudo gitlab-ctl restart
```
```
sudo cat /etc/gitlab/initial_root_password
```
