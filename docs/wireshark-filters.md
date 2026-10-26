# Useful Wireshark Display Filters

Enter these in the display-filter bar after starting or opening a capture.

| Goal | Display filter |
|---|---|
| Show DNS packets | `dns` |
| Show TCP packets | `tcp` |
| Show initial TCP SYN packets | `tcp.flags.syn == 1 && tcp.flags.ack == 0` |
| Show TCP SYN-ACK packets | `tcp.flags.syn == 1 && tcp.flags.ack == 1` |
| Show HTTP packets | `http` |
| Show TLS packets | `tls` |
| Show traffic to or from a particular IP | `ip.addr == 192.0.2.10` |

Replace example IP addresses with the address from your own capture. A display filter only filters packets already captured; it does not generate traffic. Some protocols may not appear if the capture did not include them or if the traffic uses encrypted DNS.
