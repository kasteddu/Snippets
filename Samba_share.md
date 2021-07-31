***Create a Samba Share between Rpi & Win***

Install the software :)
```bash
sudo apt-get install samba samba-common-bin
```

Go and modify conf file
```bash
sudo nano /etc/samba/smb.conf
```

Check those two lines are there, in case add/modify
```bash
workgroup = WORKGROUP
wins support = yes
```

At the bottom add the share
```bash
[PiShare]
comment=[comment] 
path= -->path to share
browseable=Yes
writeable=Yes 
only guest=no 
create mask=0777 
directory mask=0777 
public=no
```

in case, add user to share
```bash
sudo smbpasswd -a pi
```
