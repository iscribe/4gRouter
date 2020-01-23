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

- move the existing configuration file out of the way, but keep it as it containes good documentation
```
sudo mv /etc/dhcp/dhcpd.conf  /etc/dhcp/dhcpd.conf.ORIG
```

-- create a new configuration file with the following
```
vim /etc/dhcp/dhcpd.conf

ddns-update-style none;
option domain-name "4grouter";
option domain-name-servers 8.8.8.8;
default-lease-time 3600;
max-lease-time 86400;
authoritative;
log-facility local7;

# Configure service for local network 192.168.47.0 (the wireless AP)                    
subnet 192.168.2.0  netmask 255.255.255.0 {
    range 192.168.2.10 192.168.2.250;
    option routers 192.168.2.1;
}
```


