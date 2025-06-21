ip - 192.168.205.3



OS = Debian  linux 



Open-ports ==
PORT   STATE SERVICE
22/tcp open  ssh     OpenSSH 7.9p1 Debian 10+deb10u2 (protocol 2.0)
80/tcp open  http    Apache httpd 2.4.38 ((Debian))



ENUMERATING :


port 80;

we can see that on webserver this is the page is on index.html.



imp pt=  stego try kr skte h .


or we get a weird puzzle as well :


ON source side we got nothing Bad luck :









Lets try directory busting    , we may find anything ..







we get a dir /inferno  but it has a login pannel :




i dont have any other ooption aother that brute force so i tried that via hydra : 




we got success: 



adn im inside : 



okay it seems like a file server or network files manager :

okay this codiad is vuln to an RCE ⇒   [Codiad-Remote-Code-Execute-Exploit](file Q29kaWFkLVJlbW90ZS1Db2RlLUV4ZWN1dGUtRXhwbG9pdC5naXQ=)   


we take some help to run the exploit but we are inside : 





we found a hidden file 
dante:V1rg1l10h3lpm3




we got an ssh access into the  machine :
then    we foud ou a hiideen   which is called    .download.bat



i then , decode  that with hexadecimal decorder..

and got a username = password
dante:V1rg1l10h3lpm3


and got dande ssh access>  :)


a then i find   out that     /usr/bin/tee has sudo rights for root user.




and then i create a user and lohin as a root user got my flag :


steps to create a user and exploit the write permissions for /usr/bin/tee commnand


step1:  openssl passwd -1 -salt "tester" "password123"
this will give us an md5 hash as well as salt of our user : 

step2:  printf 'hello:$1$hello$Kya4ySP78J/E4OEGDrMLE1:0:0:root:/root:/bin/bash\n' | sudo tee -a /etc/passwd

this will add a new user into our passwd file :







 



 





![unnamed_82122d6743ef417889fdf5d94b2388aa](unnamed_82122d6743ef417889fdf5d94b2388aa.png)
![unnamed_59c7a4f0e44d4a1884a6cbf4b710fd4e](unnamed_59c7a4f0e44d4a1884a6cbf4b710fd4e.png)
![unnamed_6d11ebbd6317465c83e06f2a8dfd460d](unnamed_6d11ebbd6317465c83e06f2a8dfd460d.png)
![unnamed_9580977d15ed46fcaf34ba513a71fdd8](unnamed_9580977d15ed46fcaf34ba513a71fdd8.png)
![unnamed_a53aa0daf37d4681b6cdf128fc597b2c](unnamed_a53aa0daf37d4681b6cdf128fc597b2c.png)
![unnamed_190bcd37cccc44028a940d2d6bce095d](unnamed_190bcd37cccc44028a940d2d6bce095d.png)
![unnamed_c16ac6b17a0d4d69a32edeb33a8eb341](unnamed_c16ac6b17a0d4d69a32edeb33a8eb341.png)
![unnamed_bc56c5955ee3407093625e39d75be606](unnamed_bc56c5955ee3407093625e39d75be606.png)
![unnamed_68b2fdd1193f4d98a386cfe6de5ad941](unnamed_68b2fdd1193f4d98a386cfe6de5ad941.png)
