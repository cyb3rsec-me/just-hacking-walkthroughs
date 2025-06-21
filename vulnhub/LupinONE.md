 IP : 192.168.221.245
 
 open PORTS:
 PORT   STATE SERVICE VERSION
22/tcp open  ssh     OpenSSH 8.4p1 Debian 5 (protocol 2.0)
| ssh-hostkey: 
|   3072 ed:ea:d9:d3:af:19:9c:8e:4e:0f:31:db:f2:5d:12:79 (RSA)
|   256 bf:9f:a9:93:c5:87:21:a3:6b:6f:9e:e6:87:61:f5:19 (ECDSA)
|_  256 ac:18:ec:cc:35:c0:51:f5:6f:47:74:c3:01:95:b4:0f (ED25519)
80/tcp open  http    Apache httpd 2.4.48 ((Debian))
|_http-server-header: Apache/2.4.48 (Debian)
|_http-title: Site doesn't have a title (text/html).
| http-robots.txt: 1 disallowed entry 
|_/~myfiles




ENUMERATION +  info gathering

port 80 :


tp-dolist:
manual enum first
1. source -code enum
2. dir enum
3. vhost enun
4. known vuln or any unusla directoreis fiel etc
5. try owasp top 10 


web server looks like this :

running :  [Apache HTTP Server                                   2.4.48](https://www.wappalyzer.com/technologies/web-servers/apache-http-server/?utm_source=popup&utm_medium=extension&utm_campaign=wappalyzer)                 
DEBIAN OS :

source code : enum


directory indexing vuln on site:   infodisclosure



we perform nikto scan and get this :  in robots.txt



we got an error 404 :


uuu itsa a rabit hole :



after some time i decided to fuzz for files and secret :

with that ~ tilda sign :

and we fount :




okay we found this :

there is an ssh private key somwhere : 
username :   icex64



i fuzz more and after lots trial and error :
 i got this:
 
 
 
 
 
 that is base58 encoded string:
 
 
 
 and cracked with john:
 
 P@55w0rd!  : icaex64
 
 
 and got initial foothold :
 



first flag : 
 3mp!r3{I_See_That_You_Manage_To_Get_My_Bunny}
 
 
 
 priv-escalation :
 
 POST COMPROMISE ENUM -
 
 netstat ->
 
 
 users :
 
 
 
 in arsene dir : there is a note.txt :
 
 
 sudo rights :
 
 
 okay we can execute this file :
 as arsene 
 
 
 
 
 i decided to run linpeas.sh 
 
 we found something:
 
 
 
 
 okay there is a file : which we have write permissions  :
 
 
 
 
 okay : i see a write up to solve this : but i learn something new :
 
 
 
 
 
 
 
learnings :


we see we have a python file which a user   arsene can exeute as root  :



we see the contents of this : its importing a webbrowser library :
we try to locate webbrowser file :

and fount via linpeas  :


okay we have write permission for this file :

i write : 

import os
os.system ("/bin/bash")

and save that file : 

then i execute :
sudo -u arsene  /usr/bin/python3.9 /home/arsene/hack.py   


and login as arsene user : successfully :



this is called    python library hijacking :


we can learn wbout this here  :
<https://www.hackingarticles.in/linux-privilege-escalation-python-library-hijacking/>

![unnamed_5bcaf58d0428478590bf17f24809c6d5](unnamed_5bcaf58d0428478590bf17f24809c6d5.png)
![unnamed_ff8da5c74be34ed3aeb8d5e3505e92d4](unnamed_ff8da5c74be34ed3aeb8d5e3505e92d4.png)
![unnamed_75dfe30996a24974bf1c452c50fba71d](unnamed_75dfe30996a24974bf1c452c50fba71d.png)
![unnamed_c4f4a56051fe4b1cbf7290c3b2781aa0](unnamed_c4f4a56051fe4b1cbf7290c3b2781aa0.png)
![unnamed_52b731e2141747299232675f5e6798fd](unnamed_52b731e2141747299232675f5e6798fd.png)
![unnamed_7c15e5c83ca94d32b0bf99fc3e983ad1](unnamed_7c15e5c83ca94d32b0bf99fc3e983ad1.png)
![unnamed_f121820af1264e4e86360985428bd0e3](unnamed_f121820af1264e4e86360985428bd0e3.png)
![unnamed_e6e99fdb16ad4487b249c592b442b64e](unnamed_e6e99fdb16ad4487b249c592b442b64e.png)
![unnamed_30914d9ef6f44c12b416aafb2a804786](unnamed_30914d9ef6f44c12b416aafb2a804786.png)
![unnamed_e503994e82074528b3fc67499ad53208](unnamed_e503994e82074528b3fc67499ad53208.png)
![unnamed_920be4d067d34dbc963ab8f88de456f6](unnamed_920be4d067d34dbc963ab8f88de456f6.png)
![unnamed_c32cc0a78a1d487d801e0a402d352348](unnamed_c32cc0a78a1d487d801e0a402d352348.png)
![unnamed_197b874d4e62450a8ba649066e231a46](unnamed_197b874d4e62450a8ba649066e231a46.png)
![unnamed_eecfd64f55ec4cfeb37c833f77db61c5](unnamed_eecfd64f55ec4cfeb37c833f77db61c5.png)
![unnamed_15d03dc6ff17444e879897567eb87156](unnamed_15d03dc6ff17444e879897567eb87156.png)
![unnamed_f64b016e1f2f4d38844f91533b3f57e4](unnamed_f64b016e1f2f4d38844f91533b3f57e4.png)
![unnamed_18608796715e4bee9be916036fbcdd1f](unnamed_18608796715e4bee9be916036fbcdd1f.png)
![unnamed_a5a9db524f1b42e2b5406085c91b73d4](unnamed_a5a9db524f1b42e2b5406085c91b73d4.png)
![unnamed_67fb401da10b47b9923ddb2b14734fa7](unnamed_67fb401da10b47b9923ddb2b14734fa7.png)
![unnamed_6e2c6811d7894ba986721e4ac8ca51e2](unnamed_6e2c6811d7894ba986721e4ac8ca51e2.png)
![unnamed_e71a71f26d8c422f873102bf87e54c52](unnamed_e71a71f26d8c422f873102bf87e54c52.png)
![unnamed_02be189b9ece475f8c5ae1fefd237854](unnamed_02be189b9ece475f8c5ae1fefd237854.png)
![unnamed_65619f21f6ed44aaa2a2c55ac16b7e2c](unnamed_65619f21f6ed44aaa2a2c55ac16b7e2c.png)
![unnamed_c0113dcd4e6d442eb44b4b344a1a10de](unnamed_c0113dcd4e6d442eb44b4b344a1a10de.png)
![unnamed_8ae1a33ed93745b3b6d7f5a9eda8ad86](unnamed_8ae1a33ed93745b3b6d7f5a9eda8ad86.png)
![unnamed_cef71691cad640538d25392b166e1e72](unnamed_cef71691cad640538d25392b166e1e72.png)
