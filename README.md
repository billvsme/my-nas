# my-nas
my nas init and manager scripts
## tools
```
lvm
btrfs
aria2
samba
```
## install
```
sudo cp supervisor/supervisord.conf /etc/supervisor/conf.d/
sudo cp aria2/aria2.conf /etc/aria2/
sudo touch /etc/aria2/aria2.session
sudo mkdir -p /root/.cache/aria2/
git clone --depth=1 https://github.com/ziahamza/webui-aria2
```
