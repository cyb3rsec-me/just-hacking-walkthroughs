80/tcp open  http    nginx 1.15.10
|_http-title: System Tools
|_http-server-header: nginx/1.15.10





tech used: on website:


a login page is 



dire busting:

nothing found


vhosting we found nothing:


sql injection is not found:



lets try for command injection:


command injection is also not found



after a lot of recon and trial and eror i decided to go for brute force attack and i got something:







there is some functionality here :




i intercept request and lets do some changes in it :



we have command injection guys:





getting a reverse shell:









PRIVILEGE escalation:

1. we have three usernames:


charles have nothing:




jim has a backup dir :



it has old passwd list:



lets do ssh brute forcing :

we got a hit




jim:jibril04


i do some recon and i read a mail in the system for jim:



found a passwd for charles:

charles : ^xHhA&hvim0y



okay now we have some sudo -l




we can append a new use and passwd in /etc/passwd file :


step 1. create a encrypted passwd:
openssl passwd -1

step 2. copy that passwd into /etc/passwd 


step 3. login as your user:


we are root :





done :


========================================================================================
learnings :

1. always try everything else before loosing yourself , even hard methods bruteforce , passwd spray etc.
2. when u have write permission as root via any command : write write in /etc/passwd file or simply read whats in /root  dir

![unnamed_ebe56ec4201145e8ac36e71620f8dce3](unnamed_ebe56ec4201145e8ac36e71620f8dce3.png)
![unnamed_d7cda9c0f1c244d3a5f486d607c3bfe5](unnamed_d7cda9c0f1c244d3a5f486d607c3bfe5.png)
![unnamed_9f1b54f5e3b9452e9065fadabd703e92](unnamed_9f1b54f5e3b9452e9065fadabd703e92.png)
![unnamed_d83821be18194b598b8e9a170d9c5175](unnamed_d83821be18194b598b8e9a170d9c5175.png)
![unnamed_4950f74fdbd049268b85743ec839e9bf](unnamed_4950f74fdbd049268b85743ec839e9bf.png)
![unnamed_aa337657436743bab0a37933b0d530f4](unnamed_aa337657436743bab0a37933b0d530f4.png)
![unnamed_76da89b9baf64cf0afc2dc61a5aecab2](unnamed_76da89b9baf64cf0afc2dc61a5aecab2.png)
![unnamed_2ed8d375d3344c469a69d115f1aaf40b](unnamed_2ed8d375d3344c469a69d115f1aaf40b.png)
![unnamed_cdd0db372a68470c9f2f9284dc98063c](unnamed_cdd0db372a68470c9f2f9284dc98063c.png)
![unnamed_c4ea9fcc7e7c475fae9ce268ecc9ca0f](unnamed_c4ea9fcc7e7c475fae9ce268ecc9ca0f.png)
![unnamed_f4e7e519e68b4aa99025f21bfc95e6a7](unnamed_f4e7e519e68b4aa99025f21bfc95e6a7.png)
![unnamed_9e32cc2d353c42c49c5f32d837a93ccc](unnamed_9e32cc2d353c42c49c5f32d837a93ccc.png)
![unnamed_7e8a902fa2a5493ab3a2811662a6656a](unnamed_7e8a902fa2a5493ab3a2811662a6656a.png)
![unnamed_160cf11f716344ad8dd8bc22777c2e23](unnamed_160cf11f716344ad8dd8bc22777c2e23.png)
![unnamed_898dba7ed74a4cf0a81a8f4e5df1787e](unnamed_898dba7ed74a4cf0a81a8f4e5df1787e.png)
![unnamed_a72adb2d8e4547dc978cb02cae7588d5](unnamed_a72adb2d8e4547dc978cb02cae7588d5.png)
![unnamed_174320cb3baa436380f86b1c2ab7787f](unnamed_174320cb3baa436380f86b1c2ab7787f.png)
![unnamed_cd1b65f9062344dd92a486822a0781e8](unnamed_cd1b65f9062344dd92a486822a0781e8.png)
![unnamed_d55fab84502c40079a0b2fb2f16097f0](unnamed_d55fab84502c40079a0b2fb2f16097f0.png)
![unnamed_57951ec81cf24d98b73d7d55ecf9970a](unnamed_57951ec81cf24d98b73d7d55ecf9970a.png)
![unnamed_a080c187c2534374b63d1cace6ce9026](unnamed_a080c187c2534374b63d1cace6ce9026.png)
![unnamed_f91bcf5257c74e389da3cbfbf9defbe9](unnamed_f91bcf5257c74e389da3cbfbf9defbe9.png)
![unnamed_186469f70607468dafeba7ae14706d4e](unnamed_186469f70607468dafeba7ae14706d4e.png)
