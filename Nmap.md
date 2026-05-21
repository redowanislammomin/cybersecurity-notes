##PERSIONAL NOTE 
##Nmap important flags

**1.Basic scan types**
	   nmap  <ip> default scan (top 1k ports)
	* -sS  = SYN/stealth scan (fast, less detected)
	* -sT  =TCP connect scan (no root needed)
	* -sU =UDP scan (slower)
	* -sn =Ping scan — host discovery only, no ports
	* -sV =Detect service version on open ports
	* -O =Detect OS (requires root)
**2.Output & info**
	* -v =Verbose — more detail while scanning
	* -vv =Very verbose
	* -oN [filename.txt] =Save output to normal text file
	* -oX [filename.xml] =Save as XML
	* -oA basename =Save in all formats at once
	* --open =Show only open ports
**3.Port optons**
	* -p 80 =Scan specific port
	* -p 80,443,22 =Scan multiple ports
	* -p 1-1000 =Scan port range
	* -p- =Scan ALL 65535 ports
	* --top-ports [n] =Scan top [n = can be any number]  most common ports
**4.Speed & timing**
	* -T0 =Paranoid — very slow, avoids detection
	* -T1 =Sneaky
	* -T2 =Polite
	* -T3 =Normal (default)
	* -T4 =Aggressive — fast, good for CTF/labs
	* -T5 =Insane — fastest, may miss results
**5.common combos**
	* nmap -sV -sC <ip> =Version + default scripts (good starter)
	* nmap -A <ip> =Aggressive: OS + version + scripts + traceroute
	* nmap -p- -T4 <ip> =All ports, fast — good for CTF
	* nmap -sn 192.168.1.0/24 =Discover all hosts on local network
	* sudo nmap -sS -O -sV <ip> =Stealth + OS + version (full recon)
**6.Scripts (NSE)**
	* -sC =Run default safe scripts
	* --script=vuln =Check for known vulnerabilities
	* --script=http-title =Get webpage title on port 80/443
	* --script=banner =Grab service banners
	* --script=smb-vuln* =SMB vulnerability scripts (wildcard)
**Note**
--exclude <ip> — skip certain IPs when scanning a range
-iL targets.txt — scan a list of IPs from a file (useful for multiple targets)
--reason — shows WHY a port is open/closed/filtered
-Pn — skip host discovery, treat target as online (useful when host blocks ping)
--script-help <scriptname> — explains what an NSE script does before running it
