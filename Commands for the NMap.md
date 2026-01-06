# Commands for the NMap for the beginners:

#### To find the ip add 

> ifconfig

#### To scane the NMap

 nmap < target ip add >

Example:

``` 
nmap 192.168.133.1
```

<img width="1597" height="641" alt="Screenshot 2026-01-06 122447" src="https://github.com/user-attachments/assets/3ccffc68-2c16-4f7a-ab67-0db0d79a2039" />

<img width="1602" height="915" alt="Screenshot 2026-01-06 122944" src="https://github.com/user-attachments/assets/8f8ea0cb-9356-4b79-95a9-1efcff47c6c0" />

#### To Scane TCP Ports && UDP Ports

> If you scane all tcp ports on the IPadd
` sudo nmap -sT -p- < IP add >` 

>  If you scane all udp ports on the IPadd
` sudo nmap -sU -p- < IP add >`

> If you scane all tcp && udp ports on the IPadd
` sudo nmap -sT -sU -p- < IP add >` 

```
Note :- If you Scane ` sudo nmap -sT -sU -p- < IP add >` firewall detect your ip ( hacker IP ) and band it.

So don`t use this command.
````
<img width="1140" height="868" alt="Screenshot 2026-01-06 193756" src="https://github.com/user-attachments/assets/29bde180-1bfd-47a2-9152-4dfcf0d1a7d2" />

<img width="1145" height="871" alt="Screenshot 2026-01-06 193843" src="https://github.com/user-attachments/assets/03583da8-8cdb-4f80-bc1d-cc48fe0f669c" />


