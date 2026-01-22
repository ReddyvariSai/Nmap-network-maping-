# Common Port Scans
> ##### Top 1000 TCP ports (default)
> * nmap target-ip
> ##### All TCP ports
> * nmap -p- target-ip
> ##### UDP ports (slower)
> * nmap -sU -p 1-100 target-ip
> ##### Both TCP and UDP
> * nmap -sS -sU target-ip



# All TCP ports
```
                                                                                                                                 
┌──(root㉿kali)-[/]
└─# nmap -p- 192.168.133.129
Starting Nmap 7.98 ( https://nmap.org ) at 2026-01-22 04:57 -0500
Nmap scan report for 192.168.133.129
Host is up (0.21s latency).
Not shown: 65505 closed tcp ports (reset)
PORT      STATE SERVICE
21/tcp    open  ftp
22/tcp    open  ssh
23/tcp    open  telnet
25/tcp    open  smtp
53/tcp    open  domain
80/tcp    open  http
111/tcp   open  rpcbind
139/tcp   open  netbios-ssn
445/tcp   open  microsoft-ds
512/tcp   open  exec
513/tcp   open  login
514/tcp   open  shell
1099/tcp  open  rmiregistry
1524/tcp  open  ingreslock
2049/tcp  open  nfs
2121/tcp  open  ccproxy-ftp
3306/tcp  open  mysql
3632/tcp  open  distccd
5432/tcp  open  postgresql
5900/tcp  open  vnc
6000/tcp  open  X11
6667/tcp  open  irc
6697/tcp  open  ircs-u
8009/tcp  open  ajp13
8180/tcp  open  unknown
8787/tcp  open  msgsrvr
39086/tcp open  unknown
41500/tcp open  unknown
44526/tcp open  unknown
50570/tcp open  unknown
MAC Address: 00:0C:29:BA:E0:57 (VMware)

Nmap done: 1 IP address (1 host up) scanned in 77.29 seconds


                                                                                                                                    
┌──(root㉿kali)-[/]
└─# nmap -p- 192.168.133.1  
Starting Nmap 7.98 ( https://nmap.org ) at 2026-01-22 05:01 -0500

zsh: suspended  nmap -p- 192.168.133.1


```
# UDP ports (slower)
` nmap -sU -p 1-100 target-ip`
                                                                                                                                   
```                                                                                                                                   
┌──(root㉿kali)-[/]
└─# nmap -sU -p 1-100 192.168.133.129
Starting Nmap 7.98 ( https://nmap.org ) at 2026-01-22 05:14 -0500
Nmap scan report for 192.168.133.129
Host is up (0.0046s latency).
Not shown: 97 closed udp ports (port-unreach)
PORT   STATE         SERVICE
53/udp open          domain
68/udp open|filtered dhcpc
69/udp open|filtered tftp
MAC Address: 00:0C:29:BA:E0:57 (VMware)

Nmap done: 1 IP address (1 host up) scanned in 104.28 seconds
```

# Both TCP and UDP
`nmap -sS -sU target-ip`

```
──(root㉿kali)-[/]
└─# nmap -sU -sS 192.168.133.129 
Starting Nmap 7.98 ( https://nmap.org ) at 2026-01-22 05:18 -0500
Stats: 0:11:36 elapsed; 0 hosts completed (1 up), 1 undergoing UDP Scan
UDP Scan Timing: About 69.53% done; ETC: 05:34 (0:05:04 remaining)
Stats: 0:11:38 elapsed; 0 hosts completed (1 up), 1 undergoing UDP Scan
UDP Scan Timing: About 69.83% done; ETC: 05:34 (0:05:01 remaining)
Stats: 0:11:39 elapsed; 0 hosts completed (1 up), 1 undergoing UDP Scan
UDP Scan Timing: About 69.93% done; ETC: 05:34 (0:05:00 remaining)
Stats: 0:11:40 elapsed; 0 hosts completed (1 up), 1 undergoing UDP Scan
UDP Scan Timing: About 70.03% done; ETC: 05:34 (0:04:58 remaining)
Stats: 0:11:41 elapsed; 0 hosts completed (1 up), 1 undergoing UDP Scan
UDP Scan Timing: About 70.13% done; ETC: 05:34 (0:04:57 remaining)
Stats: 0:11:41 elapsed; 0 hosts completed (1 up), 1 undergoing UDP Scan
UDP Scan Timing: About 70.23% done; ETC: 05:34 (0:04:56 remaining)



```
































