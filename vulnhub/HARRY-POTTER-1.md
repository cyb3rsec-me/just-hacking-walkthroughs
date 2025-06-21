Aragog   ==> 

ip == 192.168.226.217


open-ports = 
PORT   STATE SERVICE
22/tcp open  ssh      OpenSSH 7.9p1 Debian 10+deb10u2 (protocol 2.0)
80/tcp open  http    Apache httpd 2.4.38 ((Debian))
MAC Address: 08:00:27:D5:4C:89 (Oracle VirtualBox virtual NIC)



enumeration  ===>


port 80  === 

nikto  scan =⇒ 
nikto -host <http://192.168.226.217>
- Nikto v2.5.0
---------------------------------------------------------------------------
+ Target IP:          192.168.226.217
+ Target Hostname:    192.168.226.217
+ Target Port:        80
+ Start Time:         2024-03-08 08:51:24 (GMT5.5)
---------------------------------------------------------------------------
+ Server: Apache/2.4.38 (Debian)
+ /: The anti-clickjacking X-Frame-Options header is not present. See: <https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-Frame-Options>
+ /: The X-Content-Type-Options header is not set. This could allow the user agent to render the content of the site in a different fashion to the MIME type. See: <https://www.netsparker.com/web-vulnerability-scanner/vulnerabilities/missing-content-type-header/>
+ No CGI Directories found (use '-C all' to force check all possible dirs)
+ Apache/2.4.38 appears to be outdated (current is at least Apache/2.4.54). Apache 2.2.34 is the EOL for the 2.x branch.
+ /: Server may leak inodes via ETags, header found with file /, inode: 61, size: 5bee8467b5fd6, mtime: gzip. See: <http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2003-1418>
+ OPTIONS: Allowed HTTP Methods: GET, POST, OPTIONS, HEAD .
+ /icons/README: Apache default file found. See: <https://www.vntweb.co.uk/apache-restricting-access-to-iconsreadme/>
+ /blog/wp-login.php: Cookie wordpress_test_cookie created without the httponly flag. See: <https://developer.mozilla.org/en-US/docs/Web/HTTP/Cookies>
+ /blog/wp-login.php: Wordpress login found.
+ 8102 requests: 0 error(s) and 8 item(s) reported on remote host
+ End Time:           2024-03-08 08:51:48 (GMT5.5) (24 seconds)
---------------------------------------------------------------------------




it has a image of pottre on front page ⇒ 


might be stegnography   =⇒ 







Directory busting : 




i find a dir called blog:  hmm it looks interesting. 


its a wordpress site :      version no: WordPress version 5.0.12




ok then lets enumerate this one : 

this site owners are  : 


lets enumerate some plugins : 

plugins identified ==: 

1.  twentynineteen : [!] The version is out of date, the latest version is 2.7
2.  akismet   :  
3. wp-file-manager :   [!] The version is out of date, the latest version is 7.2.4




hmm   file manager pugins have some public exploits availaible :

ok now i have RCE : 




so i use my fav metasploit to do work for me : 



got initial foothold: 


=================================================================================================================================================



Excalating Privs  +  post enumeration  :







1.    magic  spell: 
horcrux_{MTogUmlkRGxFJ3MgRGlBcnkgZEVzdHJvWWVkIEJ5IGhhUnJ5IGluIGNoYU1iRXIgb2YgU2VDcmV0cw==}
-  1: RidDlE's DiAry dEstroYed By haRry in chaMbEr of SeCrets



after some enumeration i found a wp-config file :  and 




i thing wordpress installation is placed in /etc  dir: 






i got hagrid98  creds  : 




so i crack that hash via hashcat :   and got passwd of 
hagrid98: password123



this file runs  by root user via a cronjob
hence we can exploit it becoz out hagrid98 user has write privs for this file :


PRIVILAGE excalation

i will erewrite that .backup.sh     and try to get root shelll : 


and we got root access :  yeahhhhhhhhhhh: 






2nd : magic spell :

 horcrux_{MjogbWFSdm9MbyBHYVVudCdzIHJpTmcgZGVTdHJPeWVkIGJZIERVbWJsZWRPcmU=}
 
 2: maRvoLo GaUnt's riNg deStrOyed bY DUmbledOre
 
 
 
 
 
 
 the end ::: ::::::






![unnamed_ccacd85228604f0bb5c2487e9046bc59](unnamed_ccacd85228604f0bb5c2487e9046bc59.png)
![unnamed_1cecbe00e1464d8c8cccc3ec91d00c71](unnamed_1cecbe00e1464d8c8cccc3ec91d00c71.png)
![unnamed_7efcf48fe8d64c09af4d00e8932ed6dd](unnamed_7efcf48fe8d64c09af4d00e8932ed6dd.png)
![unnamed_3bd0d98b59f64396a0cb8c7eff97acb9](unnamed_3bd0d98b59f64396a0cb8c7eff97acb9.png)
![unnamed_f13f5d7c09374c8895876b4de19ec9e5](unnamed_f13f5d7c09374c8895876b4de19ec9e5.png)
![unnamed_f414bbe593564d1cbd08b0da14f9d6ec](unnamed_f414bbe593564d1cbd08b0da14f9d6ec.png)
![unnamed_b47d55b7d7e140d8a30d17fdad5487de](unnamed_b47d55b7d7e140d8a30d17fdad5487de.png)
![unnamed_88950949fc37472c9e3733b9c578ae35](unnamed_88950949fc37472c9e3733b9c578ae35.png)
![unnamed_113330d1d5934424899088d4c06dfc6e](unnamed_113330d1d5934424899088d4c06dfc6e.png)
![unnamed_2a880510a43241ebba4344e7ee930ab0](unnamed_2a880510a43241ebba4344e7ee930ab0.png)
![unnamed_e67931f1077248659042ed0117c765b3](unnamed_e67931f1077248659042ed0117c765b3.png)
![unnamed_bacdb9653f6743ba97bd577947eb13d5](unnamed_bacdb9653f6743ba97bd577947eb13d5.png)
![unnamed_b80e46b750bc4c0e8aa4db27723e6a5f](unnamed_b80e46b750bc4c0e8aa4db27723e6a5f.png)
