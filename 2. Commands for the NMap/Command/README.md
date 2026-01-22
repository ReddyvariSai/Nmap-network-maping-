
To find a target's IP address, you need different approaches depending on the context. Here are common methods in Kali Linux:

# 1. Network Scanning (Local Network)

# Nmap - Aggressive scan 

Using nmap (Network discovery)


`# Scan entire local subnet`

```
sudo nmap -sn 192.168.1.0/24
```

`# Or specific range`

```
sudo nmap -sn 192.168.1.1-254
```


run

```                                                                                                                  
┌──(kali㉿kali)-[/]
└─$ sudo nmap -sn 192.168.133.1-254
[sudo] password for kali: 
Starting Nmap 7.98 ( https://nmap.org ) at 2026-01-22 02:41 -0500
Nmap scan report for 192.168.133.1
Host is up (0.0021s latency).
MAC Address: 00:50:56:C0:00:08 (VMware)
Nmap scan report for 192.168.133.2
Host is up (0.0020s latency).
MAC Address: 00:50:56:ED:6E:8C (VMware)
Nmap scan report for 192.168.133.254
Host is up (0.00061s latency).
MAC Address: 00:50:56:FD:44:76 (VMware)
Nmap scan report for 192.168.133.128
Host is up.
Nmap done: 254 IP addresses (4 hosts up) scanned in 4.77 seconds

```
                                      
# Using arp-scan


`# Scan local network`

```

sudo arp-scan --localnet

```

`# More detailed scan`

```

sudo arp-scan -I eth0 --localnet

```

run

```                   
┌──(kali㉿kali)-[/]
└─$ sudo arp-scan -I eth0 -l                
Interface: eth0, type: EN10MB, MAC: 00:0c:xx:xx:xx:xx, IPv4: 192.168.133.128
Starting arp-scan 1.10.0 with 256 hosts (https://github.com/royhills/arp-scan)
192.168.133.1   00:50:56:xx:xx:xx      VMware, Inc.
192.168.133.2   00:50:5:xx:xx:xx       VMware, Inc.
192.168.133.254 00:50::xx:xx:xx       VMware, Inc.

3 packets received by filter, 0 packets dropped by kernel
Ending arp-scan 1.10.0: 256 hosts scanned in 2.418 seconds (105.87 hosts/sec). 3 responded
 ```                                                                                                                   

# Using netdiscover



`# Active scan`

```
sudo netdiscover -i eth0 -r 192.168.1.0/24
```

`# Passive scan (listens for packets)`

```
sudo netdiscover -p
```

sudo netdiscover -i eth0 -r 192.168.1.0/24

<img width="713" height="206" alt="image" src="https://github.com/user-attachments/assets/f4b5a4ea-a88b-4ab4-be0e-88bce27794aa" />

## 2. If You're Connected to the Target
### Check active connections

`# Show all active connections`

```
netstat -antp
```

`# Or with ss command`

```
ss -tunap
```

`# Find connections to specific service`

```
netstat -an | grep :80
```

netstat -antp

```


                                                                                                                   
┌──(kali㉿kali)-[/]
└─$ sudo su            
┌──(root㉿kali)-[/]
└─# netstat -antp
Active Internet connections (servers and established)
Proto Recv-Q Send-Q Local Address           Foreign Address         State       PID/Program name    
tcp        0      0 127.0.0.1:33573         0.0.0.0:*               LISTEN      959/containerd

```

# 3. During an Active Session/Attack
## If you're in a system:

`# On the compromised system, find its IP`

```
ifconfig
ip addr
hostname -I
```
run 

```
┌──(root㉿kali)-[/]
└─# ifconfig
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
        RX packets 1161  bytes 252486 (246.5 KiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 2388  bytes 232650 (227.1 KiB)
        TX errors 0  dropped 6 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 1000  (Local Loopback)
        RX packets 95980  bytes 5758760 (5.4 MiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 95980  bytes 5758760 (5.4 MiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

                                                                                                                    
┌──(root㉿kali)-[/]
└─# ip add  
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host noprefixroute 
       valid_lft forever preferred_lft forever
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 00:0c:29:b4:8d:8e brd ff:ff:ff:ff:ff:ff
    inet 192.168.133.128/24 brd 192.168.133.255 scope global dynamic noprefixroute eth0
       valid_lft 1201sec preferred_lft 1201sec
    inet6 fe80::d977:813b:5b0e:53e/64 scope link noprefixroute 
       valid_lft forever preferred_lft forever
3: docker0: <NO-CARRIER,BROADCAST,MULTICAST,UP> mtu 1500 qdisc noqueue state DOWN group default 
    link/ether 02:42:40:16:05:1b brd ff:ff:ff:ff:ff:ff
    inet 172.17.0.1/16 brd 172.17.255.255 scope global docker0
       valid_lft forever preferred_lft forever
                                                                                                                    
┌──(root㉿kali)-[/]
└─# hostname -I
192.168.133.128 172.17.0.1 
```

# 4. For Website/Online Target
## Find IP of a domain

`# DNS lookup`

```
nslookup example.com
```

`# Or with dig`

```
dig example.com
```

`# Or with host`

```
host example.com
```

## Trace route to target

`# Trace path to target`

```
traceroute example.com
```

`# Or with mtr`

```

mtr example.com
```

# 5. Packet Capturing (Passive)
## Capture network traffic to find targets

`# Start Wireshark`

```
sudo wireshark
```

`# Or use tcpdump`

```
sudo tcpdump -i eth0 -n
```

# 6. Specialized Tools
## masscan for large networks

```
sudo masscan -p80 192.168.1.0/24

```

## fping for fast ping sweeps

```
fping -a -g 192.168.1.0/24 2>/dev/null
```
# Important Notes:

1. Legal considerations: Only scan networks you own or have permission to scan

2. Ethical use: Unauthorized scanning is illegal in most jurisdictions

3. Stealth scanning: Add -T flag in nmap for timing (-T0 to -T5)

4. Specify interface: Use -e eth0 or -I wlan0 if needed

## Quick Example Workflow:

`# 1. Find your network`
```
ip addr
```

`# 2. Discover local targets (if your IP is 192.168.1.10)`

```
sudo nmap -sn 192.168.1.0/24
```

`# 3. Identify specific target from the results`

> Remember: Always ensure you have proper authorization before scanning or attempting to find any target's IP address.
