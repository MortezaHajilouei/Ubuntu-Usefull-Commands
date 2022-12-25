# Ubuntu-Usefull-Commands

### Remove service
```
systemctl stop [servicename]
systemctl disable [servicename]
rm /etc/systemd/system/[servicename]
rm /etc/systemd/system/[servicename] # and symlinks that might be related
rm /usr/lib/systemd/system/[servicename] 
rm /usr/lib/systemd/system/[servicename] # and symlinks that might be related
systemctl daemon-reload
systemctl reset-failed
```

### Get port that are listenning
```
sudo lsof -i -P -n | grep LISTEN
sudo netstat -tulpn | grep LISTEN
sudo ss -tulpn | grep LISTEN
sudo lsof -i:[PORT]
sudo nmap -sTU -O [IP]
```

###  Set Proxy for docker
```
sudo mkdir /etc/systemd/system/docker.service.d
sudo nano /etc/systemd/system/docker.service.d/http-proxy.conf
```
copy below text:
```
[Service]
Environment="HTTP_PROXY=localhost:40595"
Environment="HTTPS_PROXY=localhost:40595"
Environment="SOCKS_PROXY=localhost:40595"
Environment="NO_PROXY=localhost,127.0.0.1,localaddress,.localdomain.com"
```

restart docker
```
sudo systemctl daemon-reload
sudo systemctl restart docker
```

###  remove part of files name in a folder 
```
for file in [pattern]*; do
	mv "$file" "${file/[patterb]/}"
done
```

###  disable autostart service
```
sudo systemctl disable [service] --now
```

###  clear browser cash
open panel and press ctrl + f5 or ctrl+shift+R to clear browser cache


### 
```
```
