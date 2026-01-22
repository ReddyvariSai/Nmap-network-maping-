# ifconfig 
 ifconfig is because and common & to know the ip address to the kali host. also that you know the version of the kali linux

if update and upgrade the system to easy to run and also most effisent to work on it.

 ```
sudo apt update
sudo apt upgrade -y 

```

```                                                                                                                    
┌──(kali㉿kali)-[/var/www/html]
└─$ ifconfig
docker0: flags=4099<UP,BROADCAST,MULTICAST>  mtu 1500
        inet 172.17.0.1  netmask 255.255.0.0  broadcast 172.17.255.255
        ether 02:42:40:16:05:1b  txqueuelen 0  (Ethernet) 
        RX packets 0  bytes 0 (0.0 B)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 0  bytes 0 (0.0 B)
        TX errors 0  dropped 6 overruns 0  carrier 0  collisions 0

eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
        inet 192.168.133.128  netmask 255.255.255.0  broadcast 192.168.133.255
        inet6 fe80::d977:813b:5b0e:53e  prefixlen 64  scopeid 0x20<link>
        ether 00:0c:29:b4:8d:8e  txqueuelen 1000  (Ethernet)
        RX packets 196  bytes 15236 (14.8 KiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 219  bytes 17202 (16.7 KiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 1000  (Local Loopback)
        RX packets 17552  bytes 1053120 (1.0 MiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 17552  bytes 1053120 (1.0 MiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0                                                                                                             
 ```
## nmap version

`nmap -V < system ip address >`

```
                                                                                                                  ```
┌──(kali㉿kali)-[~]
└─$ nmap -V 192.168.133.129
Nmap version 7.98 ( https://nmap.org )
Platform: x86_64-pc-linux-gnu
Compiled with: liblua-5.4.8 openssl-3.5.4 libssh2-1.11.1 libz-1.3.1 libpcre2-10.46 libpcap-1.10.5 nmap-libdnet-1.18.0 ipv6
Compiled without:
Available nsock engines: epoll poll select
```                                           
