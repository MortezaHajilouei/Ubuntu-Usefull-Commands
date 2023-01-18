# Ubuntu-Usefull-Commands

## Remove service
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

## Get port that are listenning
```
sudo lsof -i -P -n | grep LISTEN
sudo netstat -tulpn | grep LISTEN
sudo ss -tulpn | grep LISTEN
sudo lsof -i:[PORT]
sudo nmap -sTU -O [IP]
```

##  Set Proxy for docker
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

##  remove part of files name in a folder 
```
for file in [pattern]*; do
	mv "$file" "${file/[patterb]/}"
done
```

##  disable autostart service
```
sudo systemctl disable [service] --now
```

##  clear browser cash
open panel and press ctrl + f5 or ctrl+shift+R to clear browser cache


## Run terminal app with proxy
```
sudo apt install proxychains
```
Open the ProxyChains configuration file:
```
vim /etc/proxychains.conf
```
Uncomment the chaining type we want to use; in this case, dynamic_chain.
Add some proxy servers to the list.


## Get public Ip addresses
```
curl ifconfig.me
curl -4/-6 icanhazip.com
curl ipinfo.io/ip
curl api.ipify.org
curl checkip.dyndns.org
dig +short myip.opendns.com @resolver1.opendns.com
host myip.opendns.com resolver1.opendns.com
curl ident.me
curl bot.whatismyipaddress.com
curl ipecho.net/plain
```


## Get private ip address
```
ifconfig -a
ip addr (ip a)
hostname -I | awk '{print $1}'
ip route get 1.2.3.4 | awk '{print $7}'
nmcli -p device show
```



## Get process list or process with special name
```
sudo ps -aux
sudo ps -aux | grep [NAME]
```


## Configure Service to start/stop on boot with systemd
```
sudo systemctl enable [name].service
sudo systemctl disable [name].service
```

## Remove docker desktop
```
sudo apt remove docker-desktop
rm -r $HOME/.docker/desktop
sudo rm /usr/local/bin/com.docker.cli
sudo apt purge docker-desktop
```


## ...
```
```
## ...
```
```
## ...
```
```
## ...
```
```
## ...
```
```


## ...
```
```
