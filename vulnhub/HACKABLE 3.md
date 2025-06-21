IP : 192.168.185.23  

OS:  UBUNTU 


apache 2.4.46
OPEN PORTS :
80/tcp open  http
 
 
 
 
 
 ENUMERATION : 
 port 80 :
 
 
 webserver :
 
 
 
 source code :
 
 
 username :   jubiscleudo 
 
 port knocking is enabled 
 
 vhost :  dev_support
 
 
 
 dirbusting :
 
 
 some dir we found :
 
 
 lets enumerate them one by one :
 /config
 
 
 it has a base64 string :  
 
 decoded string :  
 
 
 /backup : it has a wordlist for bruteforcing :
 
 
 /imagens
 
 
 
 some pics :
 
 /login_page:
 
 
 we can try some things here : sql ; xss l command injection
 
 
 
when i try to login into the dev_suport it shows me this and then nothing : i might need to login into site first :

okay i knock port 10000 80  via knockd and see ssh is up :




lets try brute force  ssh : with their wordlist :

dev_suport
jubiscleudo

found hit :





first flag :L



privilege excalation:

1. no sudo rights 
2. no SUIDs
3. kernel versions :
4. sqldb creds


5.  there is   3.jpg file : which has a file embeded and that display : port 65535  : 


6. capabilities:


7. /usr/bin/write.ul
8. /swap.img
9. interesting files


found :password of hackable_3 user :






priv excalation to root :

running services  :


okay we found somethings L

a scripts running as root lets see if we can write into it:

okay i chech there is no   to_hackable_3.py  so i created it with my reverse sheell: 



and after some time got root  shell :





THE END:
we completed another medium boxes : 
very good


![unnamed_ef97a243578a4013bb83df2dc9f7ac34](unnamed_ef97a243578a4013bb83df2dc9f7ac34.png)
![unnamed_84708abe5a6f40e6907bb76b3aab819f](unnamed_84708abe5a6f40e6907bb76b3aab819f.png)
![unnamed_21440b2c60c646dab5bdc76046bc8b6e](unnamed_21440b2c60c646dab5bdc76046bc8b6e.png)
![unnamed_afb853ab446a46449358d130693dde91](unnamed_afb853ab446a46449358d130693dde91.png)
![unnamed_8404c280cbbc4ff4be5cc45b3a896cbd](unnamed_8404c280cbbc4ff4be5cc45b3a896cbd.png)
![unnamed_bf8999f891fe49b5901733e63830e57b](unnamed_bf8999f891fe49b5901733e63830e57b.png)
![unnamed_35d0877ab0864a6d9c23c8ac048115d6](unnamed_35d0877ab0864a6d9c23c8ac048115d6.png)
![unnamed_78570c7f89bd4c1f98cd5f14e50a7a5f](unnamed_78570c7f89bd4c1f98cd5f14e50a7a5f.png)
![unnamed_9c28f305c125434ea63359c31c1f1757](unnamed_9c28f305c125434ea63359c31c1f1757.png)
![unnamed_b6152a54151b437788b29f1c397e62b6](unnamed_b6152a54151b437788b29f1c397e62b6.png)
![unnamed_211b4478b43c40bcb7780ebfb6774896](unnamed_211b4478b43c40bcb7780ebfb6774896.png)
![unnamed_55c1deb5993c44e5abd99000e8e742f2](unnamed_55c1deb5993c44e5abd99000e8e742f2.png)
![unnamed_ff796f8089c443d89f841fe928c81d8b](unnamed_ff796f8089c443d89f841fe928c81d8b.png)
![unnamed_c02dc782c79b491ca69753764f3629ea](unnamed_c02dc782c79b491ca69753764f3629ea.png)
![unnamed_8efd7a7f4f75476cbd943aba60a5cc11](unnamed_8efd7a7f4f75476cbd943aba60a5cc11.png)
![unnamed_cf7910452cd24e48bb25233ee5bfc952](unnamed_cf7910452cd24e48bb25233ee5bfc952.png)
![unnamed_1654d800ad574256a6ec6c5556105fd4](unnamed_1654d800ad574256a6ec6c5556105fd4.png)
![unnamed_7b577d6579a14c059ab83eda92b8e0f3](unnamed_7b577d6579a14c059ab83eda92b8e0f3.png)
![unnamed_797dd24ec1a441bbba566d139b70b5bd](unnamed_797dd24ec1a441bbba566d139b70b5bd.png)
![unnamed_935d5beb8a674ad9a099eb3e1e27842f](unnamed_935d5beb8a674ad9a099eb3e1e27842f.png)
![unnamed_3343a0404c3d415f86184d23090a9a6f](unnamed_3343a0404c3d415f86184d23090a9a6f.png)
![unnamed_a16108a6eac84e8589244e8bf665eef1](unnamed_a16108a6eac84e8589244e8bf665eef1.png)
![unnamed_1dbfa699d3ea4773b195f41a7f79df3a](unnamed_1dbfa699d3ea4773b195f41a7f79df3a.png)
![unnamed_20dc023d4aee451cb6e11fede19a1a7d](unnamed_20dc023d4aee451cb6e11fede19a1a7d.png)
![unnamed_9fc5ae2534904857bbeeb84d7da7c2b1](unnamed_9fc5ae2534904857bbeeb84d7da7c2b1.png)
