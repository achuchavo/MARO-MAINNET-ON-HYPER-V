
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

#### Start SSH

```
/etc/init.d/ssh start
```

#### Stop SSH

```
/etc/init.d/ssh stop
```
