80/tcp open  http    Apache httpd
|_http-title: Welcome to DC-8 | DC-8
|_http-server-header: Apache
| http-robots.txt: 36 disallowed entries (15 shown)
| /includes/ /misc/ /modules/ /profiles/ /scripts/ 
| /themes/ /CHANGELOG.txt /cron.php /INSTALL.mysql.txt 
| /INSTALL.pgsql.txt /INSTALL.sqlite.txt /install.php /INSTALL.txt 
|_/LICENSE.txt /MAINTAINERS.txt
|_http-generator: Drupal 7 (<http://drupal.org>)

to-do list
1. dir-busting
2. virtualhosting
3. source-code exploration
4. finding hidden params via suite
5. find tech used      🆗️


tech_used:



manual-enumeration:
i just manually enumerate the site and then i found a param name nid

it has an sql injection vulnerability:




okay lets dig more :

tables:



creds :




we cracked a password:


john:turtle


first i tried to login via ssh but , not successful : i successfully login into website :



okay after some enumeration we discover that we can change form settings : then : we change format to php :



we have to edit contactus up → webform and change format to php and then we can get a reverse shell .
 
 
 
 database creds :
 
 
 ![unnamed_a26fa5a7868d44e7bca4648d1dbad90f](unnamed_a26fa5a7868d44e7bca4648d1dbad90f.png)
![unnamed_842c8c3f4be74a97983f862e9c857b1c](unnamed_842c8c3f4be74a97983f862e9c857b1c.png)
![unnamed_88e62309f1484e8ea2c11ce0f640f59d](unnamed_88e62309f1484e8ea2c11ce0f640f59d.png)
![unnamed_e958ef6e8cd548a09afe5935b8355e73](unnamed_e958ef6e8cd548a09afe5935b8355e73.png)
![unnamed_6985e8bcce554e4d838ac84d16dff43c](unnamed_6985e8bcce554e4d838ac84d16dff43c.png)
![unnamed_c13d4efa0fa84a22ae8bb422369b87df](unnamed_c13d4efa0fa84a22ae8bb422369b87df.png)
![unnamed_cdebe27084964ebc954025cb0ea9b333](unnamed_cdebe27084964ebc954025cb0ea9b333.png)
![unnamed_ab4c8a94ee6d4f1086e10294c345f637](unnamed_ab4c8a94ee6d4f1086e10294c345f637.png)
![unnamed_f25aec90e0cf453db6da4ce0d787b56e](unnamed_f25aec90e0cf453db6da4ce0d787b56e.png)
