#PASSIVE

## Services

- Whois # info about domain
- Google search

```
site:domain/subdomain
-file:txt #to exclude txt files
```

- Netcraft # shodan-like
- Wappalyzer # web technologies
- Shodan # IoT search engine
- SecurityHeaders
- Qualys SSL Labs
- GPT services

## Tools

- Whois

```
whois domain -h WHOIS_SERVER

```

- Gitleaks # find secrets inside git commits

```
# detect is deprecated in v8.19
gitleaks detect GIT_REPO -v
```

- Gitrob
- subfinder # enumerate subdomains passively

# ACTIVE

## Tools

- host # query DNS server about host info
- nslookup # host-like, deprecated on Linux

```
nslookup -type=TXT DOMAIN
```

- dig # more powerful host-like

```
dig mx DOMAIN
```

- dnsrecon # active DNS enumeration

```
dnsrecon -d DOMAIN -t std
```

- dnsenum # dnsrecon-like

```
dnsenum megacorpone.com
```

- netcat # general network utility

```
nc -nvv -w 1 -z IP_ADDR START_PORT-END_PORT # TCP primitive scanning
nc -nvv -u -z -w 1 IP_ADDR START_PORT END_PORT # UDP primitive scanning
# 2>&1 to redirect errors to stdout
```

- nmap # network scanner

```
sudo nmap -sS IP_ADDR # TCP-SYN SCAN
sudo nmap -sU IP_ADDR # UDP SCAN
sudo nmap -sS -sU IP_ADDR # TCP-SYN SCAN and UDP SCAN
nmap -sT IP_ADDR # TCP-CONNECT SCAN
nmap -sn IP_ADDR # CHECK HOST AVAILABILITY / SWEEP SCAN
nmap --script-help=all # list all scripts
# -oA output to all formats
# grep Up output to find live hosts
# -p 80 only web server on port 80
# --top-port=20 scan the first 20 in most used ports list
# -A enable OS detection, script scanning and traceroute
# -O --osscan-guess enable OS detection and prints OS guessed even if not accurate
# -sT -A good combination for banner grabbing
# --script-help SCRIPT_NAME shows info about SCRIPT
# --script http-headers script for checking supported HTTP headers
# -iL input file containing list of targets (IP, domains, ...)
# -sV service scanning
# -sC launch default scripts
```

- Test-NetConnection # PowerShell function to test network connection

```
Test-NetConnection -Port PORT IP_ADDR
```

- PowerShell network objects

```
# automated PowerShell network scanning
START_PORT..END_PORT | % {echo ((New-Object Net.Sockets.TcpClient).Connect("IP_ADDR", $_)) "TCP port $_ is open"} 2>$null
```

- ntbscan # scan networks for NetBIOS name

```
sudo nbtscan -r IP_ADDR # scan using local port 137
```

- net # Windows network management tool

```
net view \\SMB_HOST /all

```

- enum4linux # enumerate Windows and SMB information

```

```

```

```
