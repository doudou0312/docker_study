1.使用alpine基础镜像
2.安装openssh；允许root登录；生成 new host keys: RSA DSA ECDSA ED25519
(
不然会有报错：
ould not load host key: /etc/ssh/ssh_host_rsa_key
Could not load host key: /etc/ssh/ssh_host_dsa_key
Could not load host key: /etc/ssh/ssh_host_ecdsa_key
Disabling protocol version 2. Could not load host key
sshd: no hostkeys available -- exiting.
)
3.copy测试机的shadow到镜像中，root密码为123456
(因为alpine里面无法使用 echo "123456"|passwd --stdin root)
4.开放22端口
(ssh默认端口为22)
5.运行ssh
