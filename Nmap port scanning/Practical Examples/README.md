# Practical Examples

## Common Scanning Combos

`# Full port scan with service/OS detection`

```
nmap -p- -sV -O target-ip
```

`# Stealthy full scan`

```
nmap -p- -sS -T2 target-ip
```

`# Quick scan for common services`

```
nmap -T4 -F -sV target-ip

```

`# Comprehensive scan`

```
nmap -sS -sU -p- -sV -O -T4 target-ip
```

## Network Range Scans

`# Scan multiple hosts`

```
nmap 192.168.1.1 192.168.1.100
```

`# Scan subnet`
```

nmap 192.168.1.0/24

```

`# Scan IP range`

```
nmap 192.168.1.1-254
```


`# From file`

```

nmap -iL targets.txt
```

## Firewall Evasion


`# Fragment packets`

```
nmap -f target-ip
```

`# Specify MTU`

```
nmap --mtu 24 target-ip
```

`# Use decoy IPs`

```
nmap -D RND:10 target-ip
```
`# Spoof MAC address`

```
nmap --spoof-mac 0 target-ip
```

`# Source port specification`

```
nmap --source-port 53 target-ip
```

