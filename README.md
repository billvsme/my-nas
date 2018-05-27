# my-nas
my nas init and manager scripts
## tools
```
btrfs  # 磁盘文件格式
aria2  # 下载工具
webui-aria2  # aria2 网页界面
samba  # smb服务器, 配合电视的kodi
netatalk  # 苹果的afp共享, 用来Time Machine备份 
filebrowser  # 网页管理电脑的文件
```
## install
```
btrfs
sudo apt-get install btrfs-tools
sudo mkfs.btrfs /dev/sdb
sudo mount /nas /dev/sdb

aria2
sudo apt-get install aria2
sudo cp aria2/aria2.conf /etc/aria2/
sudo touch /etc/aria2/aria2.session
sudo mkdir -p /root/.cache/aria2/

webui-aria2
git clone --depth=1 https://github.com/ziahamza/webui-aria2
sudo su root
apt-get install nodejs

filebrowser
wget -qO- https://filebrowser.github.io/get.sh | bash

samba
sudo apt-get install samba
sudo cp samba/smb.conf /etc/samba/
testparm
sudo systemctl restart smbd.service

netatalk
sudo apt-get install netatalk
sudo cp netatalk/AppleVolumes.default /etc/avahi/AppleVolumes.default
sudo cp netatalk/afpd.service /etc/avahi/services
sudo systemctl restart netatalk.service

supervisor
sudo apt-get install supervisor
sudo cp supervisor/supervisord.conf /etc/supervisor/conf.d/
sudo supervisorctl -u haha -p 123 update
```
