## Router 1 ##
```console
        config t
        interface Serial1/0 
        ip address 192.168.10.1 255.255.255.0
        no shutdown
        ip route 10.2.2.0 255.255.255.0 192.168.10.2

        interface FastEthernet0/0 
        ip address 10.0.0.126 255.255.255.128
        no shutdown

        interface FastEthernet0/1
        ip address 10.0.0.254 255.255.255.128
        no shutdown
        copy running-config startup-config
``` 
## Router 2 ##

```console
        config t
        interface Serial1/0 
        ip address 192.168.10.2 255.255.255.0
        no shutdown
        ip route 10.0.0.0 255.255.255.0 192.168.10.1

        interface f0/0 
        ip address 10.2.2.126 255.255.255.128
        no shutdown

        interface f0/1
        ip address 10.2.2.254 255.255.255.128
        no shutdown
        copy running-config startup-config
``` 

### VPC's ###
```console
    1. ip 10.0.0.10/25 10.0.0.126
       save
    2  ip 10.0.0.20/25 10.0.0.126
       save
    3  ip 10.0.0.130/25 10.0.0.254
       save
    4. ip 10.2.2.10/25 10.2.2.126
       save
    5  ip 10.2.2.130/25 10.2.2.254
       save
``` 
