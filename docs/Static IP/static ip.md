= Set static IP in Ubuntu

1. Open and edit `sudo vi /etc/netplan/00-installer-config.yaml`. Don't modify `ens`

```
network:
    ethernets:
        ens160:
            addresses: []
            dhcp4: true
    version: 2


--------------------------After Configuration---------------

network:
    ethernets:
        ens160:
            addresses: [192.168.0.9/24]
            gateway4: 192.168.0.1
            nameservers:
                    addresses: [8.8.8.8,8.8.4.4]
            dhcp4: no
    version: 2
    
------------------------------OR (Recommended)-----------------------------
# This is the network config written by 'subiquity'
network:
  ethernets:
    ens160:
      addresses:
        - 192.168.0.8/24
      routes:
        - to: default
          via:  192.168.0.1
      nameservers:
        addresses:
          - 8.8.8.8
          - 8.8.4.4
        search: []
# dhcp4: true
  version: 2

```

2. Apply in debug mode

```
sudo netplan --debug apply
```
    
  
