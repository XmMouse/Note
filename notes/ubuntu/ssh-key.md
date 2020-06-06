# ssh无密码登陆
1. ssh-keygen
2. scp id_rsa.pub root@server1:/root/.ssh
3. cat id_rsa.pub >> authorized_keys
4. 删除调 id_rsa.pub 否则无法登陆到别的机器