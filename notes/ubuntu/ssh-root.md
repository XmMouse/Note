## ssh启用root
sudo vim /etc/ssh/sshd_config
PermitRootLogin yes
sudo service ssh restart