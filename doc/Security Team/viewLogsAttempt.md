##Server 140.211.89.115 Logs


I had asked David Whipp if I could view the logs for server 140.211.89.15, he told me to speak with Andrew Krug. I spoke with Andrew Krug, and was told that everyone in the class should be SUDO users and that we could access logs ourself. When trying to access said logs as SUDO through ssh, I was given this output:


[blakelyh@aenasdaq01v /]$ cd var/log/
[blakelyh@aenasdaq01v log]$ ls
anaconda.ifcfg.log    audit          cron-20121014  dracut.log        maillog-20121028   messages-20121104  samba            spooler           wtmp
anaconda.log          boot.log       cron-20121021  httpd             maillog-20121104   mysqld.log         secure           spooler-20121014  yum.log
anaconda.program.log  btmp           cron-20121028  lastlog           messages           ntpstats           secure-20121014  spooler-20121021  zabbix
anaconda.storage.log  btmp-20121101  cron-20121104  maillog           messages-20121014  prelink            secure-20121021  spooler-20121028
anaconda.syslog       ConsoleKit     dmesg          maillog-20121014  messages-20121021  puppet             secure-20121028  spooler-20121104
anaconda.yum.log      cron           dmesg.old      maillog-20121021  messages-20121028  sa                 secure-20121104  tallylog
[blakelyh@aenasdaq01v log]$ tail messages
messages           messages-20121014  messages-20121021  messages-20121028  messages-20121104  
[blakelyh@aenasdaq01v log]$ tail messages
tail: cannot open `messages' for reading: Permission denied
[blakelyh@aenasdaq01v log]$ sudo tail messages

We trust you have received the usual lecture from the local System
Administrator. It usually boils down to these three things:

    #1) Respect the privacy of others.
    #2) Think before you type.
    #3) With great power comes great responsibility.

[sudo] password for blakelyh: 
Wrong Password
cleSorry, try again.
[sudo] password for blakelyh: 
Wrong Password
Sorry, try again.
[sudo] password for blakelyh: 
blakelyh is not in the sudoers file.  This incident will be reported.
[blakelyh@aenasdaq01v log]$ 
