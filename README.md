# github
My first repository on GitHub

1.$ sudo -i       打开root权限
2.$ date -R       查看vps系统时间
3.$ cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime    vps时间与系统同步校对时间
4.$ bash <(curl -L -s https://install.direct/go.sh)        安装v2ray脚本
5.$ vi /etc/v2ray/config.json                              修改脚本配置
6.$ sudo systemctl restart v2ray                           启动v2ray
7.$ service v2ray status                                   重启v2ray

                     

                                安装bbr

1.$ yum update                                                      系统更新
2.$ cat /etc/redhat-release                                         查看系统版本
3.$ rpm --import https://www.elrepo.org/RPM-GPG-KEY-elrepo.org      安装elrepo并升级内核
    
    rpm -Uvh http://www.elrepo.org/elrepo-release-7.0-4.el7.elrepo.noarch.rpm

    yum --enablerepo=elrepo-kernel install kernel-ml -y

4.$ awk -F\' '$1=="menuentry " {print i++ " : " $2}' /etc/grub2.cfg  
5.$ grub2-set-default 0
6.$ reboot
7.$ vi /etc/sysctl.conf 
    
net.core.default_qdisc = fq
net.ipv4.tcp_congestion_control = bbr

8.$ sysctl -p

9.$ sudo yum install httpd -y
    
    sudo systemctl start httpd.service

    sudo firewall-cmd --zone=public --permanent --add-service=http

    sudo firewall-cmd --reload

    cd /var/www/html

    sudo dd if=/dev/zero of=500mb.zip bs=1024k count=500
