# Quick Reference Commands

`# Quick scan`

```
nmap -T4 -F 192.168.1.1
```

`# Full detailed scan`

```
sudo nmap -sS -sV -sC -O -p- 192.168.1.105
```

`# Stealth scan with version detection`

```
sudo nmap -sS -sV -T2 192.168.1.105
```

`# Quick UDP scan for common ports`

```
sudo nmap -sU --top-ports 100 192.168.1.105
```
