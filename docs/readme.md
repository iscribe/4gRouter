# Welcome

## Documentation
* https://iscribe.github.io/4gRouter/

```
$ lsusb
Bus 001 Device 005: ID 12d1:14dc Huawei Technologies Co., Ltd. E33372 LTE/UMTS/GSM HiLink Modem/Networkcard
Bus 001 Device 003: ID 0424:ec00 Standard Microsystems Corp. SMSC9512/9514 Fast Ethernet Adapter
Bus 001 Device 002: ID 0424:9514 Standard Microsystems Corp. SMC9514 Hub
Bus 001 Device 001: ID 1d6b:0002 Linux Foundation 2.0 root hub
```

static ip for eth0
```
$ vim /etc/network/interfaces.d/eth0

# The internal network interface
auto eth0
iface eth0 inet static
address 192.168.1.1
netmask 255.255.255.0
```

dhcp for the 4g dongle interface
```



