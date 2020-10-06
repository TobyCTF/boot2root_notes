# Tryhackmebox - Poster

## Recon

IP = 10.10.194.159

Ports = 22, 80, 5432(postgresql 9.5.8 - 9.5.10)

Box say to exploit database server.

### Metasploit magic

creds in auxiliary/scanner/postgres/postgres_login

complete service PostgreSQL 9.5.21 on x86_64-pc-linux-gnu, compiled by gcc (Ubuntu 5.4.0-6ubuntu1~16.04.12) 5.4.0 20160609, 64-bit

creds in user directory - maybe crack hashes later?

## privesc

### linpeas 

cron: *  *  * * *   root    cd /opt/ufw && bash ufw.sh

/var/www/html/config.php - creds ...

### linpeas - alison user

27(sudo) 
sudo -l and we win





