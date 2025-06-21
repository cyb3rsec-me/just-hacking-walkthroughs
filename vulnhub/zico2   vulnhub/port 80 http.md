this is a webpage looks like :




tech_stack:


todos:
- dirbusting
- fuzzing
- source-code enum  ✅️
- run burp




we enumerate source code bbut just js and css file are there only : nothing interesting


dirbutsing:



dir indexing is enabled :



i also found some dirs :





lets enumerate them one by one:




its a phpmyadmin db:


i dump all the db and i get some creds :




i cracked them :







root : 34kroot34
zico : zico2215@


itried these creds on ssh but not successful:

/pakage 






/tools dir :




it is vulnerable to LFI :







so i enumerate a liitle  bit more : and see the phpmyadmin version was used :  1.9.3 

it has some vulnerabilities : rce 

i create a new db 

test.php and a table name “exploit”

has a single fileld which has  a default value set of : 

my php revese shell :




i can access that shell:
via lfi and :
we got rce :




lets get an nc shell:

i try to get nc shell but something is blocking : i could not get  success :


so i try to enumerate from the  PHP WEB SHELL :

there are some dir : /home/zico

and in wordpress dir :


we can see wp-config.php 
has some creds :





i tried these creds ,as i thought we can reuse them to get ssh :



:

privilege escalation:




we can execute : tar & zip as root lets see if we can get root access :


and we get root : by expoiting :
zip :




DONE :

![unnamed_a646a308b53840a292dace3042073ec1](unnamed_a646a308b53840a292dace3042073ec1.png)
![unnamed_dce9aa6c1da74825b26980ef33880a89](unnamed_dce9aa6c1da74825b26980ef33880a89.png)
![unnamed_c8fd539090594eee99118139ac9f045f](unnamed_c8fd539090594eee99118139ac9f045f.png)
![unnamed_2f54ec5f96a349f4816b430edd1929d0](unnamed_2f54ec5f96a349f4816b430edd1929d0.png)
![unnamed_7d94112f2c2645f7993bcc60d7d46fb6](unnamed_7d94112f2c2645f7993bcc60d7d46fb6.png)
![unnamed_410720c8b4b3411885cd5c8ae1d78e84](unnamed_410720c8b4b3411885cd5c8ae1d78e84.png)
![unnamed_b5fa17dfbe6f4f5694a82c3177fa7f43](unnamed_b5fa17dfbe6f4f5694a82c3177fa7f43.png)
![unnamed_9d720d4d344f426eb029b56055b66d2f](unnamed_9d720d4d344f426eb029b56055b66d2f.png)
![unnamed_d7ecb60f7f4c46b484a7026b4d17199e](unnamed_d7ecb60f7f4c46b484a7026b4d17199e.png)
![unnamed_71147db810ff401aaf80df33b8553d53](unnamed_71147db810ff401aaf80df33b8553d53.png)
![unnamed_c7f7757db2bd4f5ba0f06bfdafb7971e](unnamed_c7f7757db2bd4f5ba0f06bfdafb7971e.png)
![unnamed_0cad860fc02d4ea0b28835c48bcfddb2](unnamed_0cad860fc02d4ea0b28835c48bcfddb2.png)
![unnamed_b74b292d5c834c92b8c199a7599b90d6](unnamed_b74b292d5c834c92b8c199a7599b90d6.png)
![unnamed_1f00420380b6485bac6345adb74e657c](unnamed_1f00420380b6485bac6345adb74e657c.png)
![unnamed_83eb8093dc34419eb498ba02f0e2c0a2](unnamed_83eb8093dc34419eb498ba02f0e2c0a2.png)
![unnamed_f3047458e41148e3a5b4260785e4f190](unnamed_f3047458e41148e3a5b4260785e4f190.png)
![unnamed_3d9e4d5ca2f241639598961d16f7b920](unnamed_3d9e4d5ca2f241639598961d16f7b920.png)
![unnamed_afa5bda4d3fc4cfaac0955d61c2ec50a](unnamed_afa5bda4d3fc4cfaac0955d61c2ec50a.png)
![unnamed_d6e6948b98a04ccebfd8b9061afb8e74](unnamed_d6e6948b98a04ccebfd8b9061afb8e74.png)
![unnamed_64e104f6772348c3ba593eef9227e7d8](unnamed_64e104f6772348c3ba593eef9227e7d8.png)
