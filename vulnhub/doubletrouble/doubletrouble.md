ip  → 192.168.196.202
a webserver is running =
.      [qdPM 9.1](http://qdpm.net)     




OPEN-PORTS -→ 
PORT   STATE SERVICE
22/tcp open  ssh       OpenSSH 7.9p1 Debian 10+deb10u2 (protocol 2.0)

80/tcp open  http      Apache httpd 2.4.38





enumeration ==
80 => [qdPM 9.1](http://qdpm.net)    it is vulnerable to    RCE > 


directory listing enabled → 













in /secret   dir there is a img file called doubletrouble.jpg 


so i use steghide on it , it returns error becoz of lack of passwd=    

becoz i dont have any option left , tried almost every method and got nothing :::



So i decided to crack the passwd  via       StegCracker 



after some time i got this >





so now time to exploit this MF :

i use my fav tool metasploit tool + 

and successfully got the shell -→ 







i got root accesss but theres is nota ny flags --- > it has a vm   =⇒ 




 so i download and start it 
 
 
install that in vbox and 


its name is inner

ip --=>   192.168.196.76


open-ports ⇒ 
PORT   STATE SERVICE VERSION
22/tcp open  ssh     OpenSSH 6.0p1 Debian 4+deb7u4 (protocol 2.0)
80/tcp open  http    Apache httpd 2.2.22 ((Debian))
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

php 5.5.38 




ok a webserver is running : 
which displays this form : ::: 




already checked andy directies but no luck : 
this page is vulnerable to sql injection and tried that using sqlmap and dumped the databases:L 






itried all of them to login on webpage but neither of them works 

so treied on ssh and 
clapton:ZubZub99    workds on first try  :) 

i got   an ssh access : 

and thi is user.txt









then i enumerate a little  bit   and find that    : 


this kernel version is vulnerable to a popular DirtyCow vuln  : 

so i exploit that and got root  a :)  yashhhhhh

offfff     itne mjeeeeee : 



user.txt  =  6CEA7A737C7C651F6DA7669109B5FB52

root.txt =  1B8EEA89EA92CECB931E3CC25AA8DE21




DONE WE DID IT <  I know we get a little bit help     , but itsa little bit  :  so   dont worrry         , one day will  come from then you never  will need anyone help :) .
![unnamed_aa2f0903c8a04cb5bd52d1dcf2fa96fb](unnamed_aa2f0903c8a04cb5bd52d1dcf2fa96fb.png)
![unnamed_c3cce8428ac64706a4233ddc2f1612fd](unnamed_c3cce8428ac64706a4233ddc2f1612fd.png)
![unnamed_09d837edca1b4cb382dcbf6794bfaf74](unnamed_09d837edca1b4cb382dcbf6794bfaf74.png)
![unnamed_4d6e117a930d4fee9887b62b37a91e16](unnamed_4d6e117a930d4fee9887b62b37a91e16.png)
![unnamed_07bf84a734484fae9b8677f0a47b9c59](unnamed_07bf84a734484fae9b8677f0a47b9c59.png)
![unnamed_ad8b123fee784ac59a9958541372649b](unnamed_ad8b123fee784ac59a9958541372649b.png)
![unnamed_7e391be7686a4139853941160313dab1](unnamed_7e391be7686a4139853941160313dab1.png)
![unnamed_68e2b48014d147d49f39d33fb2008db6](unnamed_68e2b48014d147d49f39d33fb2008db6.png)
![unnamed_c6ba04e173ef426bbb303d885eb538e4](unnamed_c6ba04e173ef426bbb303d885eb538e4.png)
