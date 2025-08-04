# TASK - 1

To scan our local network, (if you are using linux terminal) type in the terminal, Look for something like: inet 192.168.1.6/24, so our IP range is likely to be: 192.168.1.0/24 Now run a TCP SYN scan in the terminal, <sudo nmap -sS 192.168.1.0/24> (it might some time to load the result) Note down the open port availableo or inorder to save the result to a text format, one can run this command <nmap -sS 192.168.1.0/24 -oN .txt>

The open ports are: ftp (file transfer protocol)(21) - used to upload/ download files between the systems, DNS(domain name system) (53)- translate domain names into IP adresses, http (80) - serves unencrypted web traffic, https (443) - serves encrypted web traffic using SSL/TLS, These open ports are served using TCP protocol, except DNS where it uses both TCP/UDP protocol

The potential security risk from these open ports are: Ftp(21) -Transmits usernames/passwords in plain text - vulnerable to sniffing or MITM (Man-in-the-Middle). It an be abused for brute-force or anonymous access if misconfigured, DNS(53) - Can be used for DNS amplification attacks. If DNS is misconfigured, attackers may poison cache or exfiltrate data via DNS tunneling, Http(80) - Traffic is not encrypted, so data (including login credentials) can be intercepted. Vulnerable to web attacks like XSS, SQL injection, etc. if the web server is not secured, https(443) - More secure than HTTP, but still risky if: SSL/TLS is misconfigured or Outdated certificates used

Recommendations: Replace FTP with SFTP or FTPS, Restrict DNS to internal use; monitor for tunneling attempts, Redirect HTTP traffic to HTTPS, Regularly update SSL/TLS configurations and web application security.
