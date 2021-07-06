https://dogecoin.gg/files/dogecoin-bootstrap-2021-05-09.torrent

# **WIP do not use

to run:
./electrum-doge

![s1](https://raw.githubusercontent.com/c4pt000/docker-electrum-wallet-for-dogecoin-WIP/master/DOGE-wallet-main.png)
![s1](https://raw.githubusercontent.com/c4pt000/docker-electrum-wallet-for-dogecoin-WIP/master/doge-wallet-recv.png)
![s1](https://raw.githubusercontent.com/c4pt000/docker-electrum-wallet-for-dogecoin-WIP/master/doge-wallet-address.png)

native install
```
python2 -m pip install ecdsa
python2 -m pip install slowaes
python2 -m pip install pbkdf2
python2 -m pip install socks
python2 -m pip install PySocks
python2 -m pip install requests
python2 -m pip install pyasn1
python2 -m pip install pyasn1-modules
python2 -m pip install tlslite
python2 -m pip install btcutils
python2 -m pip install qrcode
python2 -m pip install zbar-py

wget http://mirror.centos.org/centos/7/os/x86_64/Packages/sip-devel-4.14.6-4.el7.x86_64.rpm
wget http://mirror.centos.org/centos/7/os/x86_64/Packages/sip-macros-4.14.6-4.el7.x86_64.rpm
yum install *macros*rpm
yum install sip-devel*rpm
wget http://mirror.centos.org/centos/7/os/x86_64/Packages/sip-4.14.6-4.el7.x86_64.rpm
yum install sip*rpm
wget http://mirror.centos.org/centos/7/os/x86_64/Packages/PyQt4-devel-4.10.1-13.el7.x86_64.rpm
yum install PyQt4*4.10*rpm
wget http://mirror.centos.org/centos/7/os/x86_64/Packages/PyQt4-4.10.1-13.el7.x86_64.rpm
yum install PyQt4-4.10.1-13*rpm
wget http://mirror.centos.org/centos/7/os/x86_64/Packages/dbus-python-1.1.1-9.el7.x86_64.rpm
yum install dbus-python*rpm
yum install PyQt4-4.10.1-13*rpm


  ./electrum-doge 

```


# labeled as a WIP (work in progress) 

# for dogecoin-qt synced check here https://github.com/c4pt000/dogecoin



![s1](https://raw.githubusercontent.com/c4pt000/electrum-wallet-for-dogecoin/master/donate-about-deposit.png)
```
DMq9mjF2BpWA9EZhMcpMmi6voVXiBMJY9B
```

# WIP** electrumx_connect_doge_server
# ignore previous about configuring c4pt/electrum-doge config as a rpc server


https://github.com/c4pt000/electrumx-dogecoin-server

# must only need electrumx_server to broadcast to dogecoin electrum client wallets from dogecoind synced blockchain



a script to watch dogecoin-cli getinfo to count current block count

https://raw.githubusercontent.com/c4pt000/electrum-wallet-for-dogecoin/master/watch-blocks.sh


# append to  /root/.bashrc before running electrumx_server

```
source /root/.bashrc        (for changes to take effect to .bashrc)
```

```
log info -> INFO:SessionManager:TCP server listening on all_interfaces:50111
0.0.0.0:8000 rpc
NON-SSL

/root/.bashrc
-------------------------------------
export DB_DIRECTORY=/var/electrumx-db
export DAEMON_URL=http://rpcuser:set_your_password_here@127.0.0.1:22555/
export COIN=Dogecoin
export ALLOW_ROOT=YES
export SERVICES=tcp://xx.56.96.128:50101,rpc://:8000,ssl://xx.56.96.128:50102
export SSL_CERTFILE=/opt/server.crt
export SSL_KEYFILE=/opt/server.key

#export REPORT_SERVICES=      -> for irc reporting of nodes to list nodes into an index for electrum clients

```
dogecoin blockchain snapshot (requires 80GB)
* 04-16-2021
```
yum install transmission-cli -y
cd /opt
wget https://github.com/c4pt000/electrum-wallet-for-dogecoin/raw/master/Dogecoin_Blockchain_2021-04-16.torrent
transmission-cli Dogecoin_Blockchain_2021-04-16.torrent 
cd /root/Downloads/Dogecoin_Blockchain_2021-04-16/Dogecoin
mv * /root/.dogecoin/

du -h /root/.dogecoin/
------------------------------------
588M	/root/.dogecoin/blocks/index
47G	/root/.dogecoin/blocks
731M	/root/.dogecoin/chainstate
48G	/root/.dogecoin/
-------------------------

(pruning will reduce the working blockchain to < 5GB)
with prune set

prune=2200

in /root/.dogecoin/dogecoin.conf


``` 
# pruning support of blockchain for minimal blockchain data set with electrumx_server

* for X11 to generate electrum-doge wallet
for X11 forwarding through X11 forwarding from remote VPS (requires xserver-xorg in docker vm guest)


```
mkdir /root/.XA
cp -rf /root/.Xauthority /root/.XA/

then with docker c4pt/electrum-doge (running)
from vps host to vps docker guest

cd /root
cp -rf .XA/.Xauthority /root/.Xauthority
ls /root/.Xauthority 

 
 on the VPS host before the docker c4pt/electrum-doge image is running
 for X11 graphical to generate an electrum-doge wallet
 before running cp -rf /root/.Xauthority /root/.XA/.Xauthority 
 
 
 to copy back to /root/.Xauthority inside of docker guest on remote VPS
 

requires xauth , xhost packages, xorg-server
check both sides
access control enabled, only authorized clients can connect
SI:localuser:root
```


allow 50101 out on lan firewall out
commit docker image after wallet creation

# WIP** wallet

run electrum-doge:
```
docker run -it -d --net=host -e DISPLAY=$DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix  -v /root/.XA:/root/.XA c4pt/electrum-doge

docker exec -it <docker_vm_hash> bash


electrum-doge (create wallet)
(close)
(reopen)
to view "network"
electrum-doge 

```




* for editing source of electrum-doge to change remote server connection
```
see editing c4pt/electrum-doge for server info by default
for remote electrum servers
electrum-doge.conf.sample:server = 45.56.96.128:50101:t
lib/network.py:    '45.56.96.128':DEFAULT_PORTS,
electrum-doge.conf.sample:server = 45.56.96.128:50101:t
```




```
stop current dogecoind if running:

current snapshot height  c4pt/dogecoind-current-flat
3629072
```

# for running a minimal-flat node WIP** recommended 8gb + 4 cpus 30GB



```
docker run -it -d  -v /opt/rootdogecoin:/opt/rootdogecoin c4pt/dogecoind-current-flat bash
docker exec -it <docker_vm_hash> bash
cd /root/.dogecoin
cp -rfv * /opt/rootdogecoin/
exit
mv /root/.dogecoin /root/.dogecoin.null
mkdir /root/.dogecoin
cp -rf /opt/rootdogecoin/* /root/.dogecoin/
```



# for running a full node WIP** recommended 8gb + 4 cpus 60GB
# for docker-dogecoind-full 50GB 
 
 * 04-16-2021 sync
``` 
 docker run -it -d -p 22555:22555 -p 22556:22556 c4pt/dogecoind-current-full
 
 docker exec -it <docker_vm_hash> bash
 ```
 

* dogecoin.conf: /root/.dogecoin/dogecoin.conf -> c4pt/dogecoind-current-FULL

```
prune=2200
limitfreerelay=0
dbcache=500
maxmempool=100
maxorphantx=10
                #minrelaytxfee=0.00005


The prune=2200 option will ensure that bitcoind doesn't try to save the entire 250+ GB blockchain to disk and instead prunes it as it downloads. This means that your blockchain file will be less than 1 GB. chainstate will additionally write around 5 GB to disk. Your VPS will still need to download the entire blockchain, even if it doesn't save it to disk, so make sure you have enough bandwidth.
The remaining options save RAM by limiting mempool size and requiring a fee of more than 0.00005 BTC (around $2.50). With these options, your node should use less than 500 MB RAM. However, it is recommended to allow any tx fees, so if you have more than 2 GB RAM, feel free to only keep prune=2200.



dogecoin.conf: /root/.dogecoin/dogecoin.conf -> c4pt/dogecoind-current-FULL
--------------------------------------------------------

rpcpassword=yourpasswordhere

rpcuser=rpcuser
prune=2200
mempoolexpiry=24
dbcache=2048

daemon=1

#txindex=1
#port=22556
#rpcport=22555

rpcallowip=127.0.0.1

addnode=95.85.29.144
addnode=162.243.113.110
addnode=146.185.181.114
addnode=188.165.19.28
addnode=166.78.155.36
addnode=doge.netcodepool.org
addnode=doge.cryptoculture.net
addnode=dogepool.pw
addnode=78.46.57.132

```


 




```
crontab -e
@reboot dogecoind &
@reboot electrumx_server &
```



*original electrum-doge wallet source

```
1. GETTING STARTED 
------------------
  
To run Electrum from this directory, just do:
  
  ./electrum-doge
  
  If you install Electrum on your system, you can run it from any
  directory:
  
    sudo python setup.py install
    electrum-doge
  
2. HOW OFFICIAL PACKAGES ARE CREATED
------------------------------------
python mki18n.py

pyrcc4 icons.qrc -o gui/qt/icons_rc.py

python setup.py sdist --format=zip,gztar
```
* SSL
```
$ openssl genrsa -out server.key 2048
$ openssl req -new -key server.key -out server.csr
...
Country Name (2 letter code) [AU]:US
State or Province Name (full name) [Some-State]:California
Common Name (eg, YOUR name) []: electrum-server.tld
...
A challenge password []:
...
$ openssl x509 -req -days 1825 -in server.csr -signkey server.key -out server.crt
```
