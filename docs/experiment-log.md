# Experiment Log

## Environment

- Date: 26 October 2026
- Operating System: Windows 10/11
- Tools: Nmap 7.992
- Network Interface: Not captured yet
- Setup: Testing was done on my own computer.

## Experiment 1: Nmap Local Scan

- Command used: `nmap 127.0.0.1`
- Target: My own computer (127.0.0.1)
- Open ports: 135, 445, 3306, 9080
- Services shown: msrpc, microsoft-ds, mysql, glrpc
- Screenshot: `01-nmap-localhost.png`
- What I learned: I learned how to scan my computer using Nmap and check which ports are open.

## Experiment 2 — TCP handshake

- How I generated the connection: Ran a Windows connectivity test while capturing traffic in Wireshark.
- Wireshark display filter: `tcp.stream == 3`
- SYN packet observed?: Yes
- SYN-ACK packet observed?: Yes
- ACK packet observed?: Yes
- Screenshot filename: `02-tcp-handshake.png`
- What I learned: I observed how a TCP connection starts with a three-way handshake before application data is exchanged.

## Experiment 3 — DNS lookup

- Domain or local lookup used: google.com and youtube.com
- DNS query observed?: Yes
- Query type: A and AAAA
- Response / resolved address (if visible): DNS queries and responses were visible in Wireshark. The PowerShell lookup returned IPv4 and IPv6 addresses for both domains.
- Screenshot filename: `03-dns-lookup.png`
- What I learned: I learned how DNS queries work and how A and AAAA records return IPv4 and IPv6 addresses.

## Experiment 4 — Local connectivity

- Command used: `Get-NetTCPConnection -State Listen` and `Test-NetConnection 127.0.0.1 -Port 3306`
- Local port tested: 3306
- Result: To be recorded after the connection test.
- Was a service listening?: Yes, port 3306 appeared in the listening-port output.
- Screenshot filename: `04-linux-listening-ports.png`
- What I learned: I learned how to list listening TCP ports and test whether a local service accepts connections.

## Experiment 5 — HTTP vs HTTPS

- HTTP site/service tested: Microsoft connectivity test (`www.msftconnecttest.com/connecttest.txt`)
- HTTPS site/service tested: `https://example.com/`
- What was readable in the HTTP capture: HTTP request headers and response text were visible.
- What was visible in the HTTPS capture: TLS connection details were visible, while application data was encrypted.
- Screenshot filename: `05-http-vs-https.png`
- What I learned: I learned how HTTP traffic differs from HTTPS traffic and how TLS protects application data.