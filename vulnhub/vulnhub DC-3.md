[OS]:  
[Web-Technology]:
[Hostname]:

[IP]: 192.168.253.183

[USERS]:


[CREDENTIALS]:

=========================================================================
[To-Try LIST]:
- dir busting
- virtual hosting
- source code enum
- explortation
- finding hidden inputs via burp suite


=========================================================================
[NMAP RESULTS]:
80/tcp open  http    syn-ack ttl 64 
=========================================================================
[Web Services Enumeration]:
Apache httpd 2.4.18 ((Ubuntu))
 Joomla! - Open Source Content Management

this webserver is running :


joomla version : 3.7.0


plugins installed 


we search on public explits and there is an sql injection vulnerability for this verion and we got creds



and we cracked the hash :

admin : snoopy

and login as admin:


and we upload our shell in error.php and got shell:





=========================================================================
[OTHER / PRIVILEGE-ESCALATION]:
/var/www/html/administrator/components/com_biblestudy/views/backup
[/etc/lvm/backup](fold L2V0Yy9sdm0vYmFja3Vw)
/var/www/html/media/com_biblestudy/backup
/var/www/html/tmp/install_5c96069d60a51/packages/install_5c96069d92136/admin/views/backup



database-creds:



this exploits works and we got root shell:



=========================================================================
Take Away Concepts (for the flat-file reference system):
try all exploits and techniques before seeing the walkhroughs



THE END![unnamed_0c7204f4bf7e420a93a2b280b4fda947](unnamed_0c7204f4bf7e420a93a2b280b4fda947.png)
![unnamed_3dce71fbbd494bbe98e3567e192fd5f2](unnamed_3dce71fbbd494bbe98e3567e192fd5f2.png)
![unnamed_f96133821a4f4616892d871fb99238f1](unnamed_f96133821a4f4616892d871fb99238f1.png)
![unnamed_ec5ac61d740d4db9bc36563dcd515978](unnamed_ec5ac61d740d4db9bc36563dcd515978.png)
![unnamed_8ae6cdaca97b4cf7ad76037fa74a920f](unnamed_8ae6cdaca97b4cf7ad76037fa74a920f.png)
![unnamed_10a0caf0d2e64e5ca0ed32ad9452eedc](unnamed_10a0caf0d2e64e5ca0ed32ad9452eedc.png)
![unnamed_ead97d0f53124b1d997de05916bec8d1](unnamed_ead97d0f53124b1d997de05916bec8d1.png)
![unnamed_a89b243887204ec698c075be2d1e62b3](unnamed_a89b243887204ec698c075be2d1e62b3.png)
![unnamed_2a7d774e1d8f406aa92d01c92e8f550e](unnamed_2a7d774e1d8f406aa92d01c92e8f550e.png)
