Node Setting Method   

i) Staking node  

Staking node is very simple. If you run core wallet with Renish, renish.conf and masternode.conf files are automatically created when core wallet is executed.  

Staking node can be written in the renish.conf file as follows:   

`staking=1`  

by default, we will configure renish.conf.   

```
rpcuser=E39DN0TmqD0esbybHC5gkcS7IpT3GTKt		# user defined
rpcpassword=IunRMSYpf1A6HWQmpgyPLwjuuZBbSexh		# user defined
rpcport=31001						# use RPC port
staking=1
daemon=1
server=1
port=30001						# use default port
maxconnections=128

addnode=8.8.8.8						# add a node IP address
```

To find the node IP, use the command:   

```
renish-cli masternode list
```


ii) Masternode   

Masternode configuration is a bit complicated. sometimes the configuration setting may differ depending on each cryptocurrency. this setting method described here is a common example.  

Masternode has different collateral values ??set for each cryptocurrency. and there must be the coin in the wallet equal to that collateral amount.masternode must use both renish.conf and masternode.conf files.   

Basically, in the renish.conf, you can write:   

```
masternode=1
masternodeprivkey=7VHqUc3jjdzRw2H9ifUjMrziVegcNPnhwSPaYjmzdMMf7fnExPS
```

To get masternodeprivkey, use the following command:  

```
renish-cli masternode genkey
```

And write the following in masternode.conf file.   

```
mn1 128.128.128.128:30001 7VHqUc3jjdzRw2H9ifUjMrziVegcNPnhwSPaYjmzdMMf7fnExPS dbd9536a766e13eb3badc6a9f036a2aa6f8b5ff9f30f66d126a3db3840ff4d54 0
```

```
mn1							# defined as alias.
128.128.128.128						# user's external IP
30001							# use default port
7VHqUc3jjdzRw2H9ifUjMrziVegcNPnhwSPaYjmzdMMf7fnExPS	# masternode genkey
dbd9536a766e13eb3badc6a9f036a2aa6f8b5ff9f30f66d126a3db3840ff4d54	# tx value generated when sending masternode collateral.
0							# tx order
```

To check masternode tx value and tx order value, use the following command :   

```
renish-cli masternode outputs
```

If so, renish.conf may be configured differently depending on the system version.   



* If core wallet version is 1.5 or lower   


```
rpcuser=E39DN0TmqD0esbybHC5gkcS7IpT3GTKt		# user defined
rpcpassword=IunRMSYpf1A6HWQmpgyPLwjuuZBbSexh		# user defined
rpcport=31001						# use RPC port
daemon=1
server=1
port=30001						# use default port
maxconnections=128
masternode=1
masternodeprivkey=7VHqUc3jjdzRw2H9ifUjMrziVegcNPnhwSPaYjmzdMMf7fnExPS

addnode=8.8.8.8						# add a node IP address
```


* If core wallet version is 1.6 or higher   

```
rpcuser=E39DN0TmqD0esbybHC5gkcS7IpT3GTKt		# user defined
rpcpassword=IunRMSYpf1A6HWQmpgyPLwjuuZBbSexh		# user defined
rpcport=31001						# use RPC port
daemon=1
server=1
port=30001						# use default port
maxconnections=128
masternode=1
masternodeprivkey=7VHqUc3jjdzRw2H9ifUjMrziVegcNPnhwSPaYjmzdMMf7fnExPS
externalip=128.128.128.128				# user's external ip.
masternodeaddr=128.128.128.128:30001			# user's internal/external ip and port

addnode=8.8.8.8						# add a node IP address
```

written by robinadaptor  
