80/tcp    open  http    Apache httpd 2.2.22 ((Debian))
|_http-title: Welcome to Drupal Site | Drupal Site
| http-robots.txt: 36 disallowed entries (15 shown)
| /includes/ /misc/ /modules/ /profiles/ /scripts/ 
| /themes/ /CHANGELOG.txt /cron.php /INSTALL.mysql.txt 
| /INSTALL.pgsql.txt /INSTALL.sqlite.txt /install.php /INSTALL.txt 
|_/LICENSE.txt /MAINTAINERS.txt
|_http-generator: Drupal 7 (<http://drupal.org>)
|_http-server-header: Apache/2.2.22 (Debian)





to do list:

1. dir busting
2. vhosting
3. exploraing
4. source code enum
5. find hidden inputes :





a drupal CMS is runnig


in our nmap scans we find out that drupal verision 7 is used , so i tried some exploits and one works (name Drupleaggdon)

and we have RCE:






we get a reverse shell:



step 1. i look for nc is installed or not : which nc 



step 2 : i run nc command to get a reverse shell back 




flag 1. 




flag4.txt





we find mysql db:


mysql -u dbuser --password='R0ck3t' -e 'use drupaldb; select * from users'    




admin: $S$DvQI6Y600iNeXRIeEMF94Y6FvN8nujJcEDTCP9nS5.i38jnEKuDR
Fred : $S$DWGrxef6.D0cwB5Ts.GlnLw15chRRWH2s1R3QBwC0EkvBQ/9TCGg


backup files :

$S$DAK00p3Dkojkf4O/UizYxenguXnjv





/var/www/[.bash_history](file LmJhc2hfaGlzdG9yeQ==)


and we are root becoz of find SUID :



finalflag.txt







![unnamed_a2604d00480d4517b235859c1c6929dc](unnamed_a2604d00480d4517b235859c1c6929dc.png)
![unnamed_e65a47c8d0a0447a83fd3cf2e013f150](unnamed_e65a47c8d0a0447a83fd3cf2e013f150.png)
![unnamed_8ee94131196242f5905e7444e013c310](unnamed_8ee94131196242f5905e7444e013c310.png)
![unnamed_a0bbda260b094ca49fb8e2514e7e1438](unnamed_a0bbda260b094ca49fb8e2514e7e1438.png)
![unnamed_f2ded0889db247b2a90d32896ec5f3ae](unnamed_f2ded0889db247b2a90d32896ec5f3ae.png)
![unnamed_c515e64ce741409f8b9b6e9b36a63d5b](unnamed_c515e64ce741409f8b9b6e9b36a63d5b.png)
![unnamed_7b99553ba0154a748c95c75a5608c469](unnamed_7b99553ba0154a748c95c75a5608c469.png)
![unnamed_ecc81bff5de94444a9e2b2bebe528c77](unnamed_ecc81bff5de94444a9e2b2bebe528c77.png)
![unnamed_49fcb9991ad448b2a9aa4ca31a6b6e37](unnamed_49fcb9991ad448b2a9aa4ca31a6b6e37.png)
![unnamed_3fc2cb84d4a146c3a0e543b26cdc5944](unnamed_3fc2cb84d4a146c3a0e543b26cdc5944.png)
![unnamed_641a1ba281804498ac465fbd1d05152f](unnamed_641a1ba281804498ac465fbd1d05152f.png)
![unnamed_8a9fbf0ba29d4e03bb3c8458d30c2cca](unnamed_8a9fbf0ba29d4e03bb3c8458d30c2cca.png)
![unnamed_172a1ce2956d4da0b3457a12ee970c4d](unnamed_172a1ce2956d4da0b3457a12ee970c4d.png)
