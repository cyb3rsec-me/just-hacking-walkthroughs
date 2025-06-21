IP : 

OPEN_PORTS:
PORT   STATE    SERVICE VERSION
22/tcp filtered ssh
80/tcp open     http    Apache httpd 2.4.46 ((Ubuntu))
|_http-title: Kryptos - LAN Home
| http-robots.txt: 1 disallowed entry 
|_/config
|_http-server-header: Apache/2.4.46 (Ubuntu)



port 80 enum:

to-dos=>
1. dirbusting
2. vhosthing
3. source code enum
4. test all params via burpsuite for common vulns like lfi , rfi , sql , xss , OS cmd inj .etc
5. Manual enumeration




this is aa website running:



in source code i found a clue :


jubiscleudo    => .jpg file
dev_suport@hackable3.com


this is the login page and 


and its tech_stack


apache : 2.4.46
jquery : 3.3.1


in robots.txt i found something:



it has a file called 1.txt


a bas64 endoing:


and its a port no.
 


to hit the right port and discovered the port we need ports of three combination :

80 10000   



dirbutsing:


some interesting dir we found out :




and /css/2.txt  

data is encoded with brainfuck  
its is second port :


10000 4444


after i tried some creds on login page admin:admin workds 
and i get a php script :




i fond 3.jpg and also extract third port via stegnopgraphy




now port 22 is also open ;



we have a wordlist from /backup dir :


lets do some ssh bruteforcing:

and i found something:



jubiscleudo : onlymy




NOW LETS START PRIVILEGE ESCALATION:


network interfaces :




users on system:


hackable_3
jubidcleudo : onlymy



kernel info :




routing table :



arp table :




dont have permisssion to view : hackable_3 user /home dir ::



/tmp dir:


dont have any sudo rights :



SUID & SGID:
nothing interseting in SUID :


SGID :
can have intersting:
jubiscleudo@ubuntu20:~$ find / -perm /2000 -ls 2>/dev/null
   394653      4 drwxrwsr-x   2 root     mail         4096 Apr 21  2021 /var/mail
   395072      4 drwxr-sr-x   3 root     systemd-journal     4096 Apr 27  2021 /var/log/journal
   401634      4 drwxr-sr-x   2 root     systemd-journal     4096 Nov  4 22:42 /var/log/journal/7d693ead326949a6bb91a6600cd9756f
   394651      4 drwxrwsr-x   2 root     staff               4096 Apr 19  2021 /var/local
   918098     44 -rwxr-sr-x   1 root     crontab            43720 Mar 15  2021 /usr/bin/crontab
   918163     32 -rwxr-sr-x   1 root     shadow             31312 Jan  7  2021 /usr/bin/expiry
   918719     36 -rwxr-sr-x   1 root     tty                35200 Feb 26  2021 /usr/bin/wall
   918595    256 -rwxr-sr-x   1 root     ssh               260376 Mar 23  2021 /usr/bin/ssh-agent
   918063     84 -rwxr-sr-x   1 root     shadow             84512 Jan  7  2021 /usr/bin/chage
   918732     24 -rwxr-sr-x   1 root     tty                22920 Feb 26  2021 /usr/bin/write.ul
  1054470     16 -rwxr-sr-x   1 root     utmp               14488 Dec  5  2020 /usr/lib/x86_64-linux-gnu/utempter/utempter
   924582     44 -rwxr-sr-x   1 root     shadow             43168 Aug  6  2020 /usr/sbin/pam_extrausers_chkpwd
   924634     44 -rwxr-sr-x   1 root     shadow             43160 Aug  6  2020 /usr/sbin/unix_chkpwd
      793     83 -rwxr-sr-x   1 root     shadow             84512 May 28  2020 /snap/core20/1026/usr/bin/chage
      854     31 -rwxr-sr-x   1 root     shadow             31312 May 28  2020 /snap/core20/1026/usr/bin/expiry
     1080    343 -rwxr-sr-x   1 root     crontab           350504 Mar  9  2021 /snap/core20/1026/usr/bin/ssh-agent
     1166     35 -rwxr-sr-x   1 root     tty                35048 Jul 21  2020 /snap/core20/1026/usr/bin/wall
     7169     43 -rwxr-sr-x   1 root     shadow             43168 Jul 21  2020 /snap/core20/1026/usr/sbin/pam_extrausers_chkpwd
     7213     43 -rwxr-sr-x   1 root     shadow             43160 Jul 21  2020 /snap/core20/1026/usr/sbin/unix_chkpwd
    11700      0 drwxrwsr-x   2 root     mail                   3 Apr 29  2021 /snap/core20/1026/var/mail
     1637     34 -rwxr-sr-x   1 root     shadow             34816 Jul 21  2020 /snap/core18/1997/sbin/pam_extrausers_chkpwd
     1666     34 -rwxr-sr-x   1 root     shadow             34816 Jul 21  2020 /snap/core18/1997/sbin/unix_chkpwd
     1703     71 -rwxr-sr-x   1 root     shadow             71816 Mar 22  2019 /snap/core18/1997/usr/bin/chage
     1748     23 -rwxr-sr-x   1 root     shadow             22808 Mar 22  2019 /snap/core18/1997/usr/bin/expiry
     1924    355 -rwxr-sr-x   1 root     crontab           362640 Mar  4  2019 /snap/core18/1997/usr/bin/ssh-agent
     1988     31 -rwxr-sr-x   1 root     tty                30800 Sep 16  2020 /snap/core18/1997/usr/bin/wall
    10782      0 drwxrwsr-x   2 root     mail                   3 Mar  9  2021 /snap/core18/1997/var/mail
     1639     34 -rwxr-sr-x   1 root     shadow             34816 Apr  8  2021 /snap/core18/2074/sbin/pam_extrausers_chkpwd
     1668     34 -rwxr-sr-x   1 root     shadow             34816 Apr  8  2021 /snap/core18/2074/sbin/unix_chkpwd
     1705     71 -rwxr-sr-x   1 root     shadow             71816 Mar 22  2019 /snap/core18/2074/usr/bin/chage
     1750     23 -rwxr-sr-x   1 root     shadow             22808 Mar 22  2019 /snap/core18/2074/usr/bin/expiry
     1926    355 -rwxr-sr-x   1 root     crontab           362640 Mar  4  2019 /snap/core18/2074/usr/bin/ssh-agent
     1990     31 -rwxr-sr-x   1 root     tty                30800 Sep 16  2020 /snap/core18/2074/usr/bin/wall
    10795      0 drwxrwsr-x   2 root     mail                   3 Jun 11  2021 /snap/core18/2074/var/mail
      594      0 drwxr-sr-x   2 root     systemd-journal       40 Nov  4 21:55 /run/log/journal
      
      
      
      id info :
      
      
      
      /opt dir :  have nothing
      
      
      
      /var/backups have nothing:
      
      
      
      
      
      in /var/www/html has a hidden dir :
      
      
      
      it has something interesting:
      
      
      
      hackable_3 : TrOLLED_3
      
      
      work as perfect :
      
      
      
      nothing is /home or .bash_history
      
      
      
      
      
      network info :
      
      nothing is here :
      
      
      nope no one belogs to sudoers group:
      
      
      
      
      i enumerate almost everything but noting finds :  
      
      look for anyservices : via pspy 
      
      
      
      
      
      and after some time waithing in dark i found something:
      
      
      
     oh  im so dump i missed this dir : in / root 
     
     
     
     but file is not present there so we can create python reverse shell with that name and it will execute we can get root shell:
     
     and i did it :
     
user.txt  in  /home/jubiscleudo 
      
     
     
     
     
     
     
     
       







![unnamed_c15d8b11e5544ee297e66f9dc1616f42](unnamed_c15d8b11e5544ee297e66f9dc1616f42.png)
![unnamed_e3d7728423b84131b918ff4a99c7f50c](unnamed_e3d7728423b84131b918ff4a99c7f50c.png)
![unnamed_d33df744e37f4c49a264da7c56c390ce](unnamed_d33df744e37f4c49a264da7c56c390ce.png)
![unnamed_c4618d27940b46728bc72fc53d6ede71](unnamed_c4618d27940b46728bc72fc53d6ede71.png)
![unnamed_9c756088c4b74c6cbd09ccc68eb79c83](unnamed_9c756088c4b74c6cbd09ccc68eb79c83.png)
![unnamed_140bedd2972d4327831b3327732def33](unnamed_140bedd2972d4327831b3327732def33.png)
![unnamed_6c421d0623ad4a11834cf1dd3391fb7c](unnamed_6c421d0623ad4a11834cf1dd3391fb7c.png)
![unnamed_25c3c29490034d4d8d8c0195ee09eb09](unnamed_25c3c29490034d4d8d8c0195ee09eb09.png)
![unnamed_028f65fd5966452f9afcb996fbbbc3fc](unnamed_028f65fd5966452f9afcb996fbbbc3fc.png)
![unnamed_3710e82b0c4f4ebcbf1e92649a2d32d3](unnamed_3710e82b0c4f4ebcbf1e92649a2d32d3.png)
![unnamed_dd606b498cc0431795592dc811a59466](unnamed_dd606b498cc0431795592dc811a59466.png)
![unnamed_0478974089234baf8e394b2376b7e00d](unnamed_0478974089234baf8e394b2376b7e00d.png)
![unnamed_c96a6534e60941c8acfe77bbb2ce8325](unnamed_c96a6534e60941c8acfe77bbb2ce8325.png)
![unnamed_f71172490288409bac688aa38d6fc68b](unnamed_f71172490288409bac688aa38d6fc68b.png)
![unnamed_e0327e531f564c6f83f5a80c51308bda](unnamed_e0327e531f564c6f83f5a80c51308bda.png)
![unnamed_dc258972de0941a6a78a6d82f8af184e](unnamed_dc258972de0941a6a78a6d82f8af184e.png)
![unnamed_af351932af5041d1bd6fcacd93de818c](unnamed_af351932af5041d1bd6fcacd93de818c.png)
![unnamed_5ca2c8203d98474aa037e377b6d7ee52](unnamed_5ca2c8203d98474aa037e377b6d7ee52.png)
![unnamed_18b854f85eaa46ba9268cbbc4be25ef8](unnamed_18b854f85eaa46ba9268cbbc4be25ef8.png)
![unnamed_c5606defacfb421599f8fba154dde7e4](unnamed_c5606defacfb421599f8fba154dde7e4.png)
![unnamed_e1a39083661a450c9f03e38d5a8f47a6](unnamed_e1a39083661a450c9f03e38d5a8f47a6.png)
![unnamed_a2284924c0234044a7606dde1ba0d70c](unnamed_a2284924c0234044a7606dde1ba0d70c.png)
![unnamed_97e2206158204b78ba7844d44f232517](unnamed_97e2206158204b78ba7844d44f232517.png)
![unnamed_d3f731295c03421cae0097a746128746](unnamed_d3f731295c03421cae0097a746128746.png)
![unnamed_71eea73571e84f1799e47188f9b0dbe7](unnamed_71eea73571e84f1799e47188f9b0dbe7.png)
![unnamed_01530bae3ee24377b53578af6e27ba91](unnamed_01530bae3ee24377b53578af6e27ba91.png)
![unnamed_e072902c23b34ab997a178de97eacdc3](unnamed_e072902c23b34ab997a178de97eacdc3.png)
![unnamed_3963c77d947a4b619aa4226b65c2d65c](unnamed_3963c77d947a4b619aa4226b65c2d65c.png)
![unnamed_6104bc614e9a4d89822017c98a89ac3c](unnamed_6104bc614e9a4d89822017c98a89ac3c.png)
![unnamed_bfdb1039f8594814a6cb28eda5ee8dfd](unnamed_bfdb1039f8594814a6cb28eda5ee8dfd.png)
![unnamed_0df8632e8cc54731b2727aef51f7681a](unnamed_0df8632e8cc54731b2727aef51f7681a.png)
![unnamed_470c3cba70b743b186b862edb2ada460](unnamed_470c3cba70b743b186b862edb2ada460.png)
![unnamed_3cf211891f404e5f828c96809bee2672](unnamed_3cf211891f404e5f828c96809bee2672.png)
![unnamed_914cd88a1f3441acb522c4d36645bce0](unnamed_914cd88a1f3441acb522c4d36645bce0.png)
![unnamed_329204b16ad749f594e95e0472c3b6e0](unnamed_329204b16ad749f594e95e0472c3b6e0.png)
![unnamed_19aa46c2b5424892bae301c0114e8c5f](unnamed_19aa46c2b5424892bae301c0114e8c5f.png)
![unnamed_ab3ccfdffeb744d7a84893a66f66bfda](unnamed_ab3ccfdffeb744d7a84893a66f66bfda.png)
![unnamed_2e40900e5e70466dacebac4a832b643b](unnamed_2e40900e5e70466dacebac4a832b643b.png)
