ip ==>192.168.116.199





OPEN-PORTS 

PORT     STATE SERVICE
22/tcp   open  ssh                   OpenSSH 7.9p1 Debian 10+deb10u2 (protocol 2.0)
80/tcp   open  http                  Apache httpd 2.4.38 ((Debian))    Bolt - Installation error
111/tcp  open  rpcbind          rpcbind 2-4 (RPC #100000)
2049/tcp open  nfs
8080/tcp open  http-proxy         Apache httpd 2.4.38 ((Debian))





ENUMERATION===>


port= 2049 =⇒ nfs


got a file after mounting a /srv/nfs share 
which might be a ssh private key:



port 80: 

a configuration error: or port 80


it seems a bolt software is installed on target :

so i enumerate a little bit : a directory indexing is displayed :

and contains some config files : i got some interesting info in one of them:




and i test these creds on port 8080 and login as admin



and Bolwire verion is ::::    6.03


i try to find public exploits : and i got to know that it is vuln to LFI:

and get this : 
<http://192.168.12.199:8080/dev/index.php?action.search&action=../../../../../etc/passwd>



username ⇒    jeanpaul





so i crack save.zip   from nfs   via zip2john    and got ssh private key to login


and Passphrase of id_rsa = I_love_java
now we have username and private key as well so 
lets get initial foothold :







NOw Privilage escalation : 



we can see that zip  binary has  sudo rights : 
so try to exploit that :  to get root shell :




we did it : 




NOW POST exploitation : 


dumping /etc/shadow






2. creating a new user : 
and add that to sudoers group 


hacked:hacked123 




3. clear all log files : 





DONE :


























![unnamed_94fa9e7a3aa54859bd6c864d8873ad15](unnamed_94fa9e7a3aa54859bd6c864d8873ad15.png)
![unnamed_4f92aaf57abd4e238de254d4754859e4](unnamed_4f92aaf57abd4e238de254d4754859e4.png)
![unnamed_a45b8da637094faa9f0e402c1094b00c](unnamed_a45b8da637094faa9f0e402c1094b00c.png)
![unnamed_21ca45e029d7475ea8eb070e734b26ca](unnamed_21ca45e029d7475ea8eb070e734b26ca.png)
![unnamed_62831a2b345a4be986b9f878be3084bf](unnamed_62831a2b345a4be986b9f878be3084bf.png)
![unnamed_c64b74050b0045739be8f2f41444ae9d](unnamed_c64b74050b0045739be8f2f41444ae9d.png)
![unnamed_01c47549500a446e87b4138b64d4d7a0](unnamed_01c47549500a446e87b4138b64d4d7a0.png)
![unnamed_c1ad5093e8b24bd99e05e230acf3336f](unnamed_c1ad5093e8b24bd99e05e230acf3336f.png)
![unnamed_671536b1334a45ebba5cc921921f25ee](unnamed_671536b1334a45ebba5cc921921f25ee.png)
