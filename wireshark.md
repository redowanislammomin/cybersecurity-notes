# Wireshark cheat sheet

**1.Logical operators**

&&  = AND — both conditions must match

|| =OR — either condition matches

! =NOT — exclude this condition

( ) =Group conditions together

## 2.Ip filters
	
ip.addr == x.x.x.x =Match any direction (src or dst)
	
ip.src == x.x.x.x =Only packets FROM this IP

ip.dst == x.x.x.x =Only packets TO this IP
## 3.Protocol filters
	
tcp =Show TCP traffic only

udp =Show UDP traffic only

dns =Show DNS queries (domain lookups)

http =Show unencrypted HTTP only

tls =Show encrypted TLS/HTTPS traffic

## 4.Combined filters (real use)

ip.addr == x.x.x.x && tcp =IP + TCP only

ip.addr == x.x.x.x && udp =IP + UDP only

ip.addr == x.x.x.x && (tcp || udp) =IP + both protocols

ip.addr == x.x.x.x && tcp.port == 443 =IP + HTTPS port

ip.src == x.x.x.x && !dns =From IP, exclude DNS noise

## 5.Port filters

tcp.port == 80 =HTTP port

tcp.port == 443 =HTTPS port

udp.port == 53 =DNS port

tcp.port == 22 =SSH port

## 6.What  can & cant seen
	
HTTP✓ Full headers, browser, URL, cookies
	
HTTPS/TLS✗ Encrypted — content is hidden
	
DNS✓ Domain names your device looks up

SNI ✓ Hostname leaks before encryption

QUIC ✗ YouTube uses this — fully encrypted

**NOTE**

Follow TCP/UDP stream — right click a packet → "Follow Stream" to read the full conversation

contains keyword — like http contains "password" to search inside packet content

Export packets — save specific packets to a file


