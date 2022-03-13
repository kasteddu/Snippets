# Snippets
List of useful snippest that I use once in a while and are often forgotten


Soft LInk 
create a soft link named link1 to a file named file1
```bash
 ln -s file1 link1
```

Find a word on a couple of file
```bash
 grep -rn 'parola' /dove
```

Network & Ports
```bash
 sudo netstat -anltp
 netstat -n -l
```
 
UFW
la prima da l'applicazione per tutti
La seconda e la terza sulle subnet 
usa /16 gli ultimi due
usa /24 per l'ultimo
```bash
sudo ufw allow OpenSSH
 ufw allow from 192.168.0.0/16 to any app Samba
 ufw allow from 192.168.0.0/24 to any app Samba
```
