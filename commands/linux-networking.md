# Linux Networking Commands

Use these commands on your own computer or authorized lab machine.

## Show interfaces and IP addresses

```bash
ip addr
```

## Show listening TCP ports

```bash
ss -lnt
```

## Show listening TCP and UDP sockets with process details

```bash
ss -lntup
```

Some process details may require elevated privileges.

## Scan localhost with Nmap

```bash
nmap 127.0.0.1
```

## Detect service versions on localhost

```bash
nmap -sV 127.0.0.1
```

## Test a local TCP service

```bash
nc -vz 127.0.0.1 8000
```

This last command tests port 8000 only; it does not start a service. If the port is closed, the test may fail. Record the actual result rather than treating failure as an error in the project.
