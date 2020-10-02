# Tryhackme box - Pokemon

## Recon

IP=10.10.65.22

Ports 22,80

Credentials in the default apache site... xx:xx

## Privesc

linpeas.sh findings to follow up on:

    OS: Linux version 4.15.0-112

    New path exported: /home/pokemon/bin:/home/pokemon/.local/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/usr/local/games:/snap/bin

    pkexec
    AdminIdentities=unix-group:sudo;unix-group:admin

    [+] .sh files in path
    /usr/sbin/alsa-info.sh
    /usr/bin/gettext.sh
    /usr/bin/amuFormat.sh


Nothing but a flag in webdirectory like the hint said.

find fire for another flag...

ls la ~
    Videos folder changed after creation.
    contains ash creds - ash is basicly root.









