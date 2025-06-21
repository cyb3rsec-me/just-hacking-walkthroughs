80/tcp open  http    Apache httpd 2.4.25 ((Debian))
|_http-server-header: Apache/2.4.25 (Debian)
| http-robots.txt: 22 disallowed entries (15 shown)
| /core/ /profiles/ /README.txt /web.config /admin/ 
| /comment/reply/ /filter/tips /node/add/ /search/ /user/register/ 
| /user/password/ /user/login/ /user/logout/ /index.php/admin/ 
|_/index.php/comment/reply/
|_http-title: Welcome to DC-7 | D7
|_http-generator: Drupal 8 (<https://www.drupal.org>)
MAC Address: 08:00:27:E9:55:7F (Oracle VirtualBox virtual NIC)



drupal 8 CMS is running:
web page is running:



to-dolist:
1. dirbusting
2. vshosting
3. source code enum
4. hunt params with burp


vhosting gives nothing;



itried to brute force but it has only 5 attempts:


lockout policy is only 5 attempts


I think we have to guess the password of dc7user :


we can also try sshbruteforceingchr




after so many days of enumeration : i decided to look into walkthrough :


and then 

@DCUSER when we search that on google a githhub account is displayed



in that github account : we found something:



and in config.php we can see some creds:


and those creds are resued for ssh:





privilege: escalation:


in home dir we found some mailinig files:


















THE END :

![unnamed_3d8912f53e074175ba6d41c4610728d0](unnamed_3d8912f53e074175ba6d41c4610728d0.png)
![unnamed_7cf4802cf0c14893a05456cec42f2770](unnamed_7cf4802cf0c14893a05456cec42f2770.png)
![unnamed_95f51ac306284e238508ffcb1583b321](unnamed_95f51ac306284e238508ffcb1583b321.png)
![unnamed_de41411fbf644e629bc3384b9f013f11](unnamed_de41411fbf644e629bc3384b9f013f11.png)
![unnamed_a724abbd5da848ed985f865568ee0bca](unnamed_a724abbd5da848ed985f865568ee0bca.png)
![unnamed_f11151a5c38441a09e0fba05a0537cab](unnamed_f11151a5c38441a09e0fba05a0537cab.png)
![unnamed_15f8a26f14c7451dbed51261eab8b739](unnamed_15f8a26f14c7451dbed51261eab8b739.png)
![unnamed_cfe7d26aa288440f9fe209e214ca931b](unnamed_cfe7d26aa288440f9fe209e214ca931b.png)
![unnamed_ccf940c8f2d945b199c48d1c01a5aace](unnamed_ccf940c8f2d945b199c48d1c01a5aace.png)
![unnamed_c832c4fc21774212a5eb7b6bf11d15cc](unnamed_c832c4fc21774212a5eb7b6bf11d15cc.png)
![unnamed_467f384be04046b0b77d7ec1af20b2fe](unnamed_467f384be04046b0b77d7ec1af20b2fe.png)
![unnamed_ee683c53401644f1ba981c065f895643](unnamed_ee683c53401644f1ba981c065f895643.png)
