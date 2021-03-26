
# Connect to Linux on HYPER-V from putty.

#### Install Open SSh on Linux
Run the following command to install Open SSh on linux

```
apt-get install -y openssh-server
```

#### Check Status of SSH
Run the following command to check status of SSh on linux

```
systemctl status sshd
```

#### Stop SSH

```
/etc/init.d/ssh stop
```

#### Start SSH

```
/etc/init.d/ssh start
```

#### Stop SSH

```
/etc/init.d/ssh stop
```

#### Get IP of VM Linux

```
ifconfig
```

#### Check inbound/outbound rules

```
iptables -L
```

[More Info on Inbound/Outbound rules](https://www.digitalocean.com/community/tutorials/iptables-essentials-common-firewall-rules-and-commands)


