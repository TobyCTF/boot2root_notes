# Tryhackmebox - Jacob the Boss

## Recon

IP = 10.10.180.131

ports = 
```
22/tcp    open  ssh           syn-ack
80/tcp    open  http          syn-ack
111/tcp   open  rpcbind       syn-ack
1090/tcp  open  ff-fms        syn-ack
1098/tcp  open  rmiactivation syn-ack
1099/tcp  open  rmiregistry   syn-ack
3306/tcp  open  mysql         syn-ack
3873/tcp  open  fagordnc      syn-ack
4444/tcp  open  krb524        syn-ack
4445/tcp  open  upnotifyp     syn-ack
4446/tcp  open  n1-fwp        syn-ack
4457/tcp  open  prRegister    syn-ack
4712/tcp  open  unknown       syn-ack
4713/tcp  open  pulseaudio    syn-ack
8009/tcp  open  ajp13         syn-ack
8080/tcp  open  http-proxy    syn-ack
8083/tcp  open  us-srv        syn-ack
37201/tcp open  unknown       syn-ack
46498/tcp open  unknown       syn-ack
61522/tcp open  unknown       syn-ack
```


### webserver on port 80

Webserver powered by dotclear probably version 2.16.9 (/CHANGELOG)

/admin
/db


### webserver on port 8080

jboss version 5.0.0 - Morpheus

searchsploit got working script for this version - 36575.py

## Privesc

Tried standard ways to get better shell without success

### linpeas

/srv/java/bin/java

-rw-r--r--. 1 root root 2853 Apr  1  2020 /etc/bashrc
-rw-r--r--. 1 root root 11753 Nov 27  2019 /etc/httpd/conf/httpd.conf

MySQL connection using root/NOPASS ................. Yes

find / -perm -4000 2>/dev/null
`/usr/bin/pingsys`
Nothing on gtfobins

Poking at MySQL database for a while without getting anything.

google reveals a privesc with pingsys, never ever forget about google... https://security.stackexchange.com/questions/196577/privilege-escalation-c-functions-setuid0-with-system-not-working-in-linux







