IP :  192.168.178.13

OS : UBUNTU 

Two users :



OPEN PORTS :

port 80 :  
port 22 :


PORT   STATE SERVICE VERSION
22/tcp open  ssh     OpenSSH 8.3p1 Ubuntu 1 (Ubuntu Linux; protocol 2.0)
| ssh-hostkey: 
|   3072 4b:ce:c7:5a:9c:1f:8b:cd:47:03:08:69:85:c2:91:49 (RSA)
|   256 a1:2a:a8:15:99:04:cc:2a:1e:e3:50:00:f3:55:c2:cc (ECDSA)
|_  256 2c:d3:ec:6f:4f:5b:4a:e0:ea:0a:c3:0d:2f:cb:78:17 (ED25519)
80/tcp open  http    Apache httpd 2.4.46 ((Ubuntu))
|_http-server-header: Apache/2.4.46 (Ubuntu)
|_http-title: AvadaKedavra
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel



port 80 :

web server :



okay but at last there is .php  lets do more enum and see what we got :


source code :


that .php is file inclusion :



LFI WE GOT :

okay :

we found out 2 users: 

lestrange
bellatrix


we will come later here :



i got a hind via walkthrought that we have to perform sshlogloisioning  
we can do this if we have LFi :


step1 : find out if we can view auth logs via LFI or not :

we can see them ok:


step 2 :  verify that :

i perform a login with incorect passwd :


and see we can notice login attempt in logs :



step 3 : so ssh save every success and failed attempt : we can put malicious php code in it and try login :

ssh ‘<?php system($_GET[’c']); ?>@ip-of-target


step 4 : go to location of auth.logs : 
url/var/log/auth.log&c=ifconfig

we can see output : now we can run any command we want:


whoami 




GETTING REVERSE SHELL VIA WEB_dilevery:


use exploit web delivery :
set all configs and paste commands :

copy web_dilevery paylaod : 

nad paste into your shell:




we got shell:



okay here we found a new base64 string :



its meaning is : secrets : 

i search that on a webserver and got :

password hash of  a user :  lestrange



lestrange:$6$1eIjsdebFF9/rsXH$NajEfDYUP7p/sqHdyOIFwNnltiRPwIU0L14a8zyQIdRUlAomDNrnRjTPN5Y/WirDnwMn698kIA5CV8NLdyGiY0

so i decided to crack that hash via hashcat  : and by the way this is  ::   sha266crypt



okay if hash cracked then good other wise : i doing my recon inside of dir and got first flag.txt

in bellatrix dir:




PRIVS ESCA:LATING
okay  gooting root flag : 




1. suid : have nothig


2. kernel version : have exploits but no gcc is installed :
3. sgid have nothing :


5. running linpeas: and pspy64  to get more insights about the infrastructure of the terget system :

okay im analyzing linpeas output and get something:


okay it displays soething:


okay then : we got something :


I look linpeas output more closly : and find out the there is another hidden file in secrets directory :


it contains several paswords fo i tryied to bruteforce lestrange passwd with its and got success: 



okay now ssh access : 


very good :


and we have a sudo rights for a   vim binary :


lets exploit this :

i did it man :


yeah :
root flag :




DONE MY FRIEND OSM WORK :
hello123






![unnamed_70aee4e6237b4e6ba06854a7f7e85923](unnamed_70aee4e6237b4e6ba06854a7f7e85923.png)
![unnamed_4acae28a0bd64aa1a5c3331679f160e7](unnamed_4acae28a0bd64aa1a5c3331679f160e7.png)
![unnamed_b8cdcf5a3cc94ab48f551e95699024d0](unnamed_b8cdcf5a3cc94ab48f551e95699024d0.png)
![unnamed_71217b48e67f439fb4ebed2b25f6dd3d](unnamed_71217b48e67f439fb4ebed2b25f6dd3d.png)
![unnamed_292fe0facc7241149221cc240d379273](unnamed_292fe0facc7241149221cc240d379273.png)
![unnamed_19a16a83b9484c0da4e952586cdb66c4](unnamed_19a16a83b9484c0da4e952586cdb66c4.png)
![unnamed_2841321faa494d4fbd7b37a6bbd65632](unnamed_2841321faa494d4fbd7b37a6bbd65632.png)
![unnamed_98bcae7a65d04735a967bbae8248b773](unnamed_98bcae7a65d04735a967bbae8248b773.png)
![unnamed_0a040f6f1c1647318d9281a594159550](unnamed_0a040f6f1c1647318d9281a594159550.png)
![unnamed_da3daba671dd4aff90c2f41c564f9e91](unnamed_da3daba671dd4aff90c2f41c564f9e91.png)
![unnamed_9a5755969db14de798e4d06b1d9bc208](unnamed_9a5755969db14de798e4d06b1d9bc208.png)
![unnamed_d09b84358c4b45979fdf2ef8e8e9d4a9](unnamed_d09b84358c4b45979fdf2ef8e8e9d4a9.png)
![unnamed_6624b5ddb69141749422f299666c5967](unnamed_6624b5ddb69141749422f299666c5967.png)
![unnamed_3e2f4f44511948199d26b37ee4b70c18](unnamed_3e2f4f44511948199d26b37ee4b70c18.png)
![unnamed_d3b925514c284c4292b100101f2c29e6](unnamed_d3b925514c284c4292b100101f2c29e6.png)
![unnamed_9d09da1c5a41429590dcf54207d370fb](unnamed_9d09da1c5a41429590dcf54207d370fb.png)
![unnamed_88fa1d5024794526ba14a85fec874a3b](unnamed_88fa1d5024794526ba14a85fec874a3b.png)
![unnamed_461aeab1c89a4ac5a2611dfd55cd4065](unnamed_461aeab1c89a4ac5a2611dfd55cd4065.png)
![unnamed_f8d5f7f955074cacb1be7ff6ab9b23c7](unnamed_f8d5f7f955074cacb1be7ff6ab9b23c7.png)
![unnamed_2230b4a557824f0693bed47064f8c915](unnamed_2230b4a557824f0693bed47064f8c915.png)
![unnamed_1fe3e50fb168400ba2ff11158cd72a8d](unnamed_1fe3e50fb168400ba2ff11158cd72a8d.png)
![unnamed_fdb1d85caa3a4bf891db955b1a676199](unnamed_fdb1d85caa3a4bf891db955b1a676199.png)
![unnamed_5ba21975806c441087afde90d374cc87](unnamed_5ba21975806c441087afde90d374cc87.png)
![unnamed_98d5a5770f9b4eb884139f3d4476910c](unnamed_98d5a5770f9b4eb884139f3d4476910c.png)
![unnamed_6a4145db941846aaa1911b2949f5e580](unnamed_6a4145db941846aaa1911b2949f5e580.png)
