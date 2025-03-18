---
aliases:
  - Nmap
  - Network mapper
---
Nmap, full name Network Mapper.

Scan volgorde:
nmap -sP scan
Dan specifiek nmap -sS -A --script vuln IP.Addr

## NetworkChuck covered switches
Source: [nmap tutorial to find network vulnerabilities](https://www.youtube.com/watch?v=4t4kBkMsDbQ)

| Switch | Purpose                                                                                                                                    | Example                                      |
| ------ | ------------------------------------------------------------------------------------------------------------------------------------------ | -------------------------------------------- |
| -sP    | Pings all addresses in the given range.                                                                                                    | nmap <u>-sP</u> 10.10.10.0/24                |
| -p     | Allows you to specify ports, seperated with a comma                                                                                        | sudo nmap -sT <u>-p 80,443</u> 10.10.10.0/24 |
| -sT    | A TCP connect scan. This scan checks if the 3-way-handshake from TCP can be made.                                                          | sudo nmap <u>-sT</u> -p 80,443 10.10.10.0/24 |
| -sS    | A stealthy version of the -sT switch. This runs a three-way-handshake but never establishes the connection by not finishing the handshake. | sudo nmap <u>-sS</u> -p 80,443 10.10.10.0/24 |
| -A     | Will do OS detection, version detection, script scanning and trace route                                                                   |                                              |
| -D     | -D can be used for decoy IP addresses, thus obfuscating what is done and where from.                                                       | sudo nmap -sS -D decoy_IP target_IP          |

sudo nmap --script vuln target_IP
- Does a scan with a number of scripts for vulnerabilities.
- It analyses the found information against CVE's. Likely will make breaking in much, much easier.

## Additional switches of interest

| nmap switch | description      | nmap switch | description                                                                                                                                                          |
| ----------- | ---------------- | ----------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| -sA         | ACK scan         | -PI         | ICMP ping                                                                                                                                                            |
| -sF         | FIN scan         | -Po         | No ping                                                                                                                                                              |
| -sI         | IDLE scan        | -PS         | SYN ping                                                                                                                                                             |
| -sL         | DNS or list scan | -PT         | TCP ping                                                                                                                                                             |
| -sN         | NULL scan **?**  | -oN         | Normal output                                                                                                                                                        |
| -sO         | Protocol scan    | -oX         | XML output                                                                                                                                                           |
| -sP         | Ping scan        | -T<0-5>     | Set a timing template, with higher numbers being faster.                                                                                                             |
| -sR         | RPC scan **?**   |             | A timing template is the time nmap waits for. Higher numbers thus mean that the scan is faster, but also far easier to spot.                                         |
| -sS         | SYN scan         |             | Lower numbers subsequently do get stealthier.<br>There is a DRASTIC difference in speed however. If time is of the essence use T5, otherwise leave it standard (T3). |
| -sT         | TCP connect scan |             |                                                                                                                                                                      |
| -sW         | Window scan      |             |                                                                                                                                                                      |
| -sX         | XMAS scan        |             |                                                                                                                                                                      |
