Understanding the /proc filesystem.

Proc is a pseudo filesystem that is generally mounted as /proc. It provides an interface into the kernel data structures. Proc contains a directory of each of the process-id’s running on the system. Inside each of the process-id directory you can find out additional information about the process. For instance if you need to know about all the file descriptors which a process has open, you can ls /proc//fd . For instance, let’s say you look at rsyslog:

1
2
3
4
5
6
7
8
9
$ pgrep rsyslog
1405
$ ls -l /proc/1405/fd
total 0
lrwx------ 1 root root 64 May  6 00:20 0 -> socket:[11792]
l-wx------ 1 root root 64 May  6 00:20 1 -> /var/log/messages
l-wx------ 1 root root 64 May  6 00:20 2 -> /var/log/cron
lr-x------ 1 root root 64 May  6 00:20 3 -> /proc/kmsg
l-wx------ 1 root root 64 May  6 00:20 4 -> /var/log/secure
Rsyslog is running with process-id 1405, when I do an ‘ls -l /proc/1405/fd’ I can see that rsyslog has /var/log/messages open, which makes sense since rsyslog writes messages to /var/log/messages.

If you want to know which environment variables a process is running with you can ‘ (cat /proc//environ; echo) | tr ’00’ ‘\n’. In the above example, let’s say I want to see which environment variables rsyslog started with:

1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
$  (cat /proc/1405/environ; echo) | tr '\000' '\n'
TERM=linux
PATH=/sbin:/usr/sbin:/bin:/usr/bin
runlevel=3
RUNLEVEL=3
LANGSH_SOURCED=1
PWD=/
LANG=en_US.UTF-8
previous=N
PREVLEVEL=N
CONSOLETYPE=serial
SHLVL=3
UPSTART_INSTANCE=
UPSTART_EVENTS=runlevel
UPSTART_JOB=rc
_=/sbin/rsyslogd
If you want to know the path of the binary that was executed try the below:

1
2
$ ls -l /proc/1405/exe
lrwxrwxrwx 1 root root 0 May  5 22:36 /proc/1405/exe -> /sbin/rsyslogd
Each process has certain limits that are generally defined in /etc/security/limits.conf. Some of these can be viewed in /proc//limits file. In the rsyslog example here is the output of the file:

1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
[root@hv1 proc]# cat 1405/limits 
Limit                     Soft Limit           Hard Limit           Units     
Max cpu time              unlimited            unlimited            seconds   
Max file size             unlimited            unlimited            bytes     
Max data size             unlimited            unlimited            bytes     
Max stack size            10485760             unlimited            bytes     
Max core file size        0                    unlimited            bytes     
Max resident set          unlimited            unlimited            bytes     
Max processes             127212               127212               processes 
Max open files            1024                 4096                 files     
Max locked memory         65536                65536                bytes     
Max address space         unlimited            unlimited            bytes     
Max file locks            unlimited            unlimited            locks     
Max pending signals       127212               127212               signals   
Max msgqueue size         819200               819200               bytes     
Max nice priority         0                    0                    
Max realtime priority     0                    0                    
Max realtime timeout      unlimited            unlimited            us        

