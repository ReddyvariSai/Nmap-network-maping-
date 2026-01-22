# Timing & Performance

## Timing Templates

`# Paranoid (T0) - Very slow, stealthy`

```

nmap -T0 target-ip
```

`# Sneaky (T1)`

```
nmap -T1 target-ip

```

`# Polite (T2)`

```

nmap -T2 target-ip
```

`# Normal (T3) - Default`

```
nmap -T3 target-ip
```

`# Aggressive (T4) - Faster`

```
nmap -T4 target-ip
```

`# Insane (T5) - Very fast, noisy`

```
nmap -T5 target-ip
```

## Performance Options

`# Faster scan with timing`

```

nmap -T4 -F target-ip
```

`# Minimum rate (packets per second)`

```
nmap --min-rate 100 target-ip
```

`# Maximum rate`

```
nmap --max-rate 1000 target-ip
```

`# Don't ping (assume host is up)`

```

nmap -Pn target-ip

```
