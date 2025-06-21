IP : 192.168.95.111

OS : linux 


OPEN_PORTS:
PORT     STATE SERVICE            VERSION
25/tcp   open  smtp               Postfix smtpd
| ssl-cert: Subject: commonName=straylight
| Subject Alternative Name: DNS:straylight
| Not valid before: 2018-05-12T18:08:02
|_Not valid after:  2028-05-09T18:08:02
|_ssl-date: TLS randomness does not represent time
|_smtp-commands: straylight, PIPELINING, SIZE 10240000, VRFY, ETRN, STARTTLS, ENHANCEDSTATUSCODES, 8BITMIME, DSN, SMTPUTF8
80/tcp   open  http               Apache httpd 2.4.25 ((Debian))
|_http-server-header: Apache/2.4.25 (Debian)
|_http-title: Night City
3000/tcp open  hadoop-tasktracker Apache Hadoop
| hadoop-tasktracker-info: 
|_  Logs: submit
|_http-trane-info: Problem with XML parsing of /evox/about
| http-title: Welcome to ntopng
|_Requested resource was /lua/login.lua?referer=/
| hadoop-datanode-info: 
|_  Logs: submit



