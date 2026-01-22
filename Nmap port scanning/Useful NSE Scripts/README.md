# Common Script Examples

`# Vulnerability scan`

```
nmap --script vuln target-ip
```

`# Brute force detection`

```
nmap --script brute target-ip
```

`# Safe scripts only`

```
nmap --script safe target-ip
```

`# Multiple script categories`

```
nmap --script "vuln and safe" target-ip
```
