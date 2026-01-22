# Advanced Scanning

## Service/Version Detection

`# Service version detection`

```
nmap -sV target-ip
```

`# Aggressive version detection`

```
nmap -sV --version-intensity 9 target-ip
```

`# Light version detection`

```
nmap -sV --version-intensity 0 target-ip
```

# OS Detection

`# OS detection`

```
nmap -O target-ip
```

`# Aggressive OS detection`


```
nmap -O --osscan-guess target-ip
```


# Script Scanning

`# Default script scan`

```
nmap -sC target-ip
```

`# Specific script category`

```

nmap --script=vuln target-ip

nmap --script=auth target-ip

nmap --script=exploit target-ip
```

`# Individual script`

```
nmap --script=http-title target-ip
```


