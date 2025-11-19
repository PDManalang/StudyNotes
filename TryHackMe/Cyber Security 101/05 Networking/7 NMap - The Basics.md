# 7 NMap - The Basics

## 7.2 Host Discovery: Who is Online
- NMap ways to specify targets:
    - IP Range `-`, if you want to scan all IP addresses from 192.168.0.1 to 192.168.0.10 you can write `192.168.0.1-10`
    - IP Subnet `/`, if you want to scan a subnet it can be expressed as `192.168.0.1/24` - this would be equivalent to 192.168.0.0-255
    - Hostname, can also be specified for example `example.thm`
- NMap offers `-sn` option to discover online hosts on a network (much broad than `ping`)