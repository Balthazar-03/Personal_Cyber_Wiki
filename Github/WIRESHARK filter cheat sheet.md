## BASIS PROTOCOL FILTERS

|            |                            |
| ---------- | -------------------------- |
| TCP        | Toon alleen TCP verkeer    |
| UDP        | Toon alleen UDP verkeer    |
| HTTP       | Toon HTTP verkeer          |
| DNS        | Toon DNS verkeer           |
| FTP        | Toon FTP verkeer           |
| SSH        | Toon SSH verkeer<br>       |
| SSL of TLS | Toon HTTPS/SSL/TLS verkeer |
| ICMP       | Toon ICMP verkeer (ping)   |
| !ARP       | Verberg ARP verkeer        |
| telnet     | Toon Telnet verkeer        |

## IP FILTERS

|                          |                     |
| ------------------------ | ------------------- |
| Ip.addr == 10.10.10.1    | Verkeer van/naar IP |
| Ip.src == 10.10.10.1     | Verkeer vanaf IP    |
| Ip.dst == 10.10.10.1     | Verkeer naar IP     |
| Ip.addr == 10.10.10.0/24 | Verkeer in subnet   |

## PORT FILTERS

|                      |                                |
| -------------------- | ------------------------------ |
| Tcp.port == 80       | Verkeer op TCP poort 80        |
| Udp.port == 53       | Verkeer op UDP poort 53        |
| Tcp.port in {80 443} | Verkeer op TCP poort 80 OF 443 |
| Tcp.dstport == 80    | Verkeer naar poort 80          |
| Tcp.srcport == 80    | Verkeer vanaf poort 80         |

## HTTP FILTERS

|                                   |                           |
| --------------------------------- | ------------------------- |
| http.request                      | Toon HTTP requests        |
| http.response                     | Toon HTTP responses       |
| http.request.method == “POST”     | HTTP POST requests        |
| http.request.method == “GET”      | HTTP GET requests         |
| http.host contains “google”       | HTTP naar specifieke host |
| http.user_agent contains “curl”   | Specifieke user agent     |
| http.request.uri contains “admin” | URLs met “admin”          |

## DNS FILTERS

|                                |                         |
| ------------------------------ | ----------------------- |
| Dns.qry.name contains “google” | DNS queries voor google |
| Dns.qry.type == 1              | DNS A record queries    |
| Dns.flags.response == 1        | DNS antwoorden          |
| Dns.qry.name.len > 50          | Lange DNS queries       |

## TCP FILTERS

|                             |                 |
| --------------------------- | --------------- |
| Tcp.flags.syn == 1          | SYN packets     |
| Tcp.flags.ack == 1          | ACK packets     |
| Tcp.flags.reset == 1        | RST packets     |
| Tcp.window_size == 0        | Zero window     |
| Tcp.flags.fin == 1          | FIN packets     |
| Tcp.analysis.retransmission | Retransmissions |

## COMBINATIE FILTERS

|                                         |                              |
| --------------------------------------- | ---------------------------- |
| http \|\| https                         | HTTP of HTTPS verkeer        |
| tcp.port == 80 && ip.addr == 10.10.10.1 | HTTP van/naar IP             |
| !(arp \|\| dns)                         | Geen ARP en DNS verkeer      |
| http.request && tcp.port != 80          | HTTP op niet-standaard poort |

## GROOTTE FILTERS

|                  |                    |
| ---------------- | ------------------ |
| Frame.len > 1500 | Grote packets      |
| Frame.len < 64   | Kleine packets     |
| Ip.ttl < 10      | Bijna verlopen TTL |

## ERROR FILTERS

|                          |               |
| ------------------------ | ------------- |
| http.response.code > 399 | HTTP errors   |
| tcp.analysis.flags       | TCP problemen |
| icmp.type == 3           | ICMP errors   |

## HANDIGE FILTERS VOOR SECURITY

|                                                 |                   |
| ----------------------------------------------- | ----------------- |
| Tcp.flags.syn == 1 && tcp.flags.ack == 0        | SYN scans         |
| Dns.qry.name contains “exe”                     | EXE in DNS        |
| Tls && tcp.port != 443                          | TLS op rare poort |
| Smb \|\| nbns \|\| dcerpc                       | Windows verkeer   |
| http.request.method == “POST” && http.file_data | File uploads      |
| ftp-data \|\| tftp                              | File transfers    |

## OPERATORS

|          |                           |
| -------- | ------------------------- |
| ==       | Gelijk aan                |
| !=       | Niet gelijk aan           |
| >        | Groter dan                |
| <        | Kleiner dan               |
| >=       | Groter dan of gelijk aan  |
| <=       | Kleiner dan of gelijk aan |
| &&       | AND                       |
| \|\|     | OR                        |
| !        | NOT                       |
| Contains | Bevat tekst               |
| Matches  | Matches regex             |
