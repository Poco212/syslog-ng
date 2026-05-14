# preparation

```
sudo pacman -S syslog-ng
```
```
sudo systemctl enable syslog-ng@default.service
```
```
sudo systemctl start syslog-ng@default.service
```

# testing

```
sudo nvim /etc/syslog-ng/syslog-ng.conf 
```
find section `log` and uncomment. example : 

```
log {
	source(s_local);
	filter(f_everything);
	destination(d_everything);
};

```
```
sudo systemctl restart syslog-ng@default.service
```
```
logger "TES: Sekarang file log sudah aktif"
```
check result

```
sudo cat /var/log/everything.log
```
result
```
May 14 22:34:21 system user[39759]: TES: Sekarang file everything log sudah aktif
```
