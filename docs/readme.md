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

### static ip for eth0
```
$ vim /etc/dhcpcd.conf

## add the following
interface eth0
  static ip_address 192.168.2.1/24
  
$ sudo service dhcpcd restart
```

### dhcp server
- install isc-dhcp-server


