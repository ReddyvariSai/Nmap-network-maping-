# Basic Port Scanning

## 1. Default Scan (Top 1000 ports)

```
nmap target-ip

```
Example: nmap `192.168.1.105`

```

┌──(root㉿kali)-[/]
└─# sudo arp-scan --localnet    
Interface: eth0, type: EN10MB, MAC: 00:0c:29:b4:8d:8e, IPv4: 192.168.133.128
Starting arp-scan 1.10.0 with 256 hosts (https://github.com/royhills/arp-scan)
192.168.133.1   00:50:56:c0:00:08       VMware, Inc.
192.168.133.2   00:50:56:ed:6e:8c       VMware, Inc.
192.168.133.254 00:50:56:fd:44:76       VMware, Inc.

3 packets received by filter, 0 packets dropped by kernel
Ending arp-scan 1.10.0: 256 hosts scanned in 2.481 seconds (103.18 hosts/sec). 3 responded



──(root㉿kali)-[/]
└─# nmap 192.168.133.1 
Starting Nmap 7.98 ( https://nmap.org ) at 2026-01-22 03:46 -0500
Nmap scan report for 192.168.133.1
Host is up (0.0013s latency).
All 1000 scanned ports on 192.168.133.1 are in ignored states.
Not shown: 1000 filtered tcp ports (no-response)
MAC Address: 00:50:56:C0:00:08 (VMware)

Nmap done: 1 IP address (1 host up) scanned in 22.07 seconds

```

<img width="718" height="317" alt="image" src="https://github.com/user-attachments/assets/991bc3d8-1930-40b8-8f88-d855d152a6fb" />

```
                                                                                                                    
┌──(root㉿kali)-[/]
└─# nmap -p 80 192.168.133.129
Starting Nmap 7.98 ( https://nmap.org ) at 2026-01-22 03:55 -0500
Nmap scan report for 192.168.133.129
Host is up (0.0031s latency).

PORT   STATE SERVICE
80/tcp open  http
MAC Address: 00:0C:29:BA:E0:57 (VMware)

Nmap done: 1 IP address (1 host up) scanned in 1.26 seconds

```

# port 1-100

### metasploitable2
```
                                                                                                                   
┌──(root㉿kali)-[/]
└─# nmap -p 1-100 192.168.133.129
Starting Nmap 7.98 ( https://nmap.org ) at 2026-01-22 04:00 -0500
Nmap scan report for 192.168.133.129
Host is up (0.011s latency).
Not shown: 94 closed tcp ports (reset)
PORT   STATE SERVICE
21/tcp open  ftp
22/tcp open  ssh
23/tcp open  telnet
25/tcp open  smtp
53/tcp open  domain
80/tcp open  http
MAC Address: 00:0C:29:BA:E0:57 (VMware)

Nmap done: 1 IP address (1 host up) scanned in 1.58 seconds
```

### windows security appled system

```                                                                                                                
┌──(root㉿kali)-[/]
└─# nmap -p 1-100 192.168.133.1  
Starting Nmap 7.98 ( https://nmap.org ) at 2026-01-22 04:00 -0500
Nmap scan report for 192.168.133.1
Host is up (0.00092s latency).
All 100 scanned ports on 192.168.133.1 are in ignored states.
Not shown: 100 filtered tcp ports (no-response)
MAC Address: 00:50:56:C0:00:08 (VMware)

Nmap done: 1 IP address (1 host up) scanned in 4.02 seconds

```

# Scan Types (TCP)
## Stealth Scans

> ###### SYN scan (half-open) - Most common
> * nmap -sS target-ip
> ###### FIN scan
> * nmap -sF target-ip
> ###### XMAS scan (FIN, PSH, URG flags)
> * nmap -sX target-ip
> ###### NULL scan (no flags)
> * nmap -sN target-ip

# SYN scane
### metasploitable2

```
                                                                                                                   
┌──(root㉿kali)-[/]
└─# nmap -sS 192.168.133.129
Starting Nmap 7.98 ( https://nmap.org ) at 2026-01-22 04:12 -0500
Nmap scan report for 192.168.133.129
Host is up (0.13s latency).
Not shown: 977 closed tcp ports (reset)
PORT     STATE SERVICE
21/tcp   open  ftp
22/tcp   open  ssh
23/tcp   open  telnet
25/tcp   open  smtp
53/tcp   open  domain
80/tcp   open  http
111/tcp  open  rpcbind
139/tcp  open  netbios-ssn
445/tcp  open  microsoft-ds
512/tcp  open  exec
513/tcp  open  login
514/tcp  open  shell
1099/tcp open  rmiregistry
1524/tcp open  ingreslock
2049/tcp open  nfs
2121/tcp open  ccproxy-ftp
3306/tcp open  mysql
5432/tcp open  postgresql
5900/tcp open  vnc
6000/tcp open  X11
6667/tcp open  irc
8009/tcp open  ajp13
8180/tcp open  unknown
MAC Address: 00:0C:29:BA:E0:57 (VMware)

Nmap done: 1 IP address (1 host up) scanned in 3.11 seconds
```
### windows security appled system


```                                                                                                                    
┌──(root㉿kali)-[/]
└─# nmap -sS 192.168.133.1  
Starting Nmap 7.98 ( https://nmap.org ) at 2026-01-22 04:12 -0500
Nmap scan report for 192.168.133.1
Host is up (0.0066s latency).
All 1000 scanned ports on 192.168.133.1 are in ignored states.
Not shown: 1000 filtered tcp ports (no-response)
MAC Address: 00:50:56:C0:00:08 (VMware)

Nmap done: 1 IP address (1 host up) scanned in 23.16 seconds
                                                              
```

nmap -sF target -ip

# FIN scane
### metasploitable2

`nmap -sF 192.168.133.129`


```                                                                                                                    
┌──(root㉿kali)-[/]
└─# nmap -sF 192.168.133.129
Starting Nmap 7.98 ( https://nmap.org ) at 2026-01-22 04:19 -0500
Nmap scan report for 192.168.133.129
Host is up (0.029s latency).
Not shown: 977 closed tcp ports (reset)
PORT     STATE         SERVICE
21/tcp   open|filtered ftp
22/tcp   open|filtered ssh
23/tcp   open|filtered telnet
25/tcp   open|filtered smtp
53/tcp   open|filtered domain
80/tcp   open|filtered http
111/tcp  open|filtered rpcbind
139/tcp  open|filtered netbios-ssn
445/tcp  open|filtered microsoft-ds
512/tcp  open|filtered exec
513/tcp  open|filtered login
514/tcp  open|filtered shell
1099/tcp open|filtered rmiregistry
1524/tcp open|filtered ingreslock
2049/tcp open|filtered nfs
2121/tcp open|filtered ccproxy-ftp
3306/tcp open|filtered mysql
5432/tcp open|filtered postgresql
5900/tcp open|filtered vnc
6000/tcp open|filtered X11
6667/tcp open|filtered irc
8009/tcp open|filtered ajp13
8180/tcp open|filtered unknown
MAC Address: 00:0C:29:BA:E0:57 (VMware)

Nmap done: 1 IP address (1 host up) scanned in 3.28 seconds
                                          
```

### windows security appled system

`nmap -sF 192.168.133.1`

```                                                                                                                    
┌──(root㉿kali)-[/]
└─# nmap -sF 192.168.133.1
Starting Nmap 7.98 ( https://nmap.org ) at 2026-01-22 04:18 -0500
Nmap scan report for 192.168.133.1
Host is up (0.0072s latency).
All 1000 scanned ports on 192.168.133.1 are in ignored states.
Not shown: 1000 open|filtered tcp ports (no-response)
MAC Address: 00:50:56:C0:00:08 (VMware)

Nmap done: 1 IP address (1 host up) scanned in 22.60 seconds
```
# XMAS scan ( FIN, PSH, URG flags)

`nmap -sX target-ip`


```

──(root㉿kali)-[/]
└─# nmap -sX 192.168.133.1
Starting Nmap 7.98 ( https://nmap.org ) at 2026-01-22 04:25 -0500
Nmap scan report for 192.168.133.1
Host is up (0.0010s latency).
All 1000 scanned ports on 192.168.133.1 are in ignored states.
Not shown: 1000 open|filtered tcp ports (no-response)
MAC Address: 00:50:56:C0:00:08 (VMware)

Nmap done: 1 IP address (1 host up) scanned in 24.73 seconds
                                                                                                                    
┌──(root㉿kali)-[/]
└─# nmap -sX 192.168.133.129
Starting Nmap 7.98 ( https://nmap.org ) at 2026-01-22 04:32 -0500
Nmap scan report for 192.168.133.129
Host is up (0.048s latency).
Not shown: 977 closed tcp ports (reset)
PORT     STATE         SERVICE
21/tcp   open|filtered ftp
22/tcp   open|filtered ssh
23/tcp   open|filtered telnet
25/tcp   open|filtered smtp
53/tcp   open|filtered domain
80/tcp   open|filtered http
111/tcp  open|filtered rpcbind
139/tcp  open|filtered netbios-ssn
445/tcp  open|filtered microsoft-ds
512/tcp  open|filtered exec
513/tcp  open|filtered login
514/tcp  open|filtered shell
1099/tcp open|filtered rmiregistry
1524/tcp open|filtered ingreslock
2049/tcp open|filtered nfs
2121/tcp open|filtered ccproxy-ftp
3306/tcp open|filtered mysql
5432/tcp open|filtered postgresql
5900/tcp open|filtered vnc
6000/tcp open|filtered X11
6667/tcp open|filtered irc
8009/tcp open|filtered ajp13
8180/tcp open|filtered unknown
MAC Address: 00:0C:29:BA:E0:57 (VMware)

Nmap done: 1 IP address (1 host up) scanned in 3.73 seconds
                                                                  

```

# NULL scan (no flags)

`nmap -sN target-ip`

```
                                                                                                                   
┌──(root㉿kali)-[/]
└─# nmap -sN 192.168.133.1 
Starting Nmap 7.98 ( https://nmap.org ) at 2026-01-22 04:43 -0500
Nmap scan report for 192.168.133.1
Host is up (0.015s latency).
All 1000 scanned ports on 192.168.133.1 are in ignored states.
Not shown: 1000 open|filtered tcp ports (no-response)
MAC Address: 00:50:56:C0:00:08 (VMware)

Nmap done: 1 IP address (1 host up) scanned in 29.24 seconds
                                                                                                                                    
┌──(root㉿kali)-[/]
└─# nmap -sN 192.168.133.129
Starting Nmap 7.98 ( https://nmap.org ) at 2026-01-22 04:44 -0500
Nmap scan report for 192.168.133.129
Host is up (0.012s latency).
Not shown: 977 closed tcp ports (reset)
PORT     STATE         SERVICE
21/tcp   open|filtered ftp
22/tcp   open|filtered ssh
23/tcp   open|filtered telnet
25/tcp   open|filtered smtp
53/tcp   open|filtered domain
80/tcp   open|filtered http
111/tcp  open|filtered rpcbind
139/tcp  open|filtered netbios-ssn
445/tcp  open|filtered microsoft-ds
512/tcp  open|filtered exec
513/tcp  open|filtered login
514/tcp  open|filtered shell
1099/tcp open|filtered rmiregistry
1524/tcp open|filtered ingreslock
2049/tcp open|filtered nfs
2121/tcp open|filtered ccproxy-ftp
3306/tcp open|filtered mysql
5432/tcp open|filtered postgresql
5900/tcp open|filtered vnc
6000/tcp open|filtered X11
6667/tcp open|filtered irc
8009/tcp open|filtered ajp13
8180/tcp open|filtered unknown
MAC Address: 00:0C:29:BA:E0:57 (VMware)

Nmap done: 1 IP address (1 host up) scanned in 4.21 seconds


```
























