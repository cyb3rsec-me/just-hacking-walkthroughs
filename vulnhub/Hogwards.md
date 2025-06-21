IP :  192.168.145.215


OS : LINUX


OPEN PORTS :
80/tcp open  http    Apache httpd 2.4.46 ((Ubuntu))

during nmap scan :we got a base64 string :




Username :    Draco   and  Potter


source code :
we found a dir 



lets see what have there :




php is also installed :





we found a hidden directory :



log   : and there is  a  saved passwords :


okay another dir :  /DiagonAlley

on that dir : there is wordpress site is running :


tech used :


wordpress 5.5.3 : 


its brainfuck encodings :


decrypted text :


wp-login page :
<http://192.168.145.215/DiagonAlley/wp-login.php>

okay we have to search for draco's house name : on internet :

## name of the draco‚Äôs house   :   ans is    

**Slytherin**


and we login :






INITIAL FOOTHOLD :
lets upload reverse shell:
we uplaod shell on 404.php theme editor template :






flag 1 :





POST enum:

wordpress DB name :
'


got shadow file : via exploiting SUID base32 :




i explit base32  SUID : bascially i ran linpeas : which gave my file name of root flag and the i got it 













i get root : i have tried soooo manythings : 


but my mistake was :  not using absolute path :

eg: 

step 1 : i create a binry :



step 2 : i used absolute path:



step 3:  i am root





DONE ![unnamed_8d40bd62d27742819343eeae109a9d7a](unnamed_8d40bd62d27742819343eeae109a9d7a.png)
![unnamed_b8be0035b2a74052a55d7c8c8451b2a6](unnamed_b8be0035b2a74052a55d7c8c8451b2a6.png)
![unnamed_6b91734a5b53464db75e40b45b15248b](unnamed_6b91734a5b53464db75e40b45b15248b.png)
![unnamed_5da5dfdf19e843e89c837745b12dab1f](unnamed_5da5dfdf19e843e89c837745b12dab1f.png)
![unnamed_d143eed5ae7c4d8a8ea4d0ff7b69ea6c](unnamed_d143eed5ae7c4d8a8ea4d0ff7b69ea6c.png)
![unnamed_4837a7ea06074a70a285725aaa817935](unnamed_4837a7ea06074a70a285725aaa817935.png)
![unnamed_c0df99e1c7c24b7b953623500d9ab876](unnamed_c0df99e1c7c24b7b953623500d9ab876.png)
![unnamed_8bdd0907feae479582e660c053af5957](unnamed_8bdd0907feae479582e660c053af5957.png)
![unnamed_5fe4e7fde7c14be387bf8c621d868aab](unnamed_5fe4e7fde7c14be387bf8c621d868aab.png)
![unnamed_c0b64e991d5f48cda0ed4984b7053ac5](unnamed_c0b64e991d5f48cda0ed4984b7053ac5.png)
![unnamed_76118277612e4dac874f7fb5fbdc859c](unnamed_76118277612e4dac874f7fb5fbdc859c.png)
![unnamed_587336e4ed5441b7a9da74040e4a5932](unnamed_587336e4ed5441b7a9da74040e4a5932.png)
![unnamed_8c875b7e3c654d1285aee4826e0cb628](unnamed_8c875b7e3c654d1285aee4826e0cb628.png)
![unnamed_eeb457b9dd89473ca79d1ea91eb89315](unnamed_eeb457b9dd89473ca79d1ea91eb89315.png)
![unnamed_9c60a7e3fe3e486badbc780ea520a4ec](unnamed_9c60a7e3fe3e486badbc780ea520a4ec.png)
![unnamed_24352d69285846a6acebaa057fc6fdcc](unnamed_24352d69285846a6acebaa057fc6fdcc.png)
![unnamed_75afc12dd3fd43dd9cf4385d0ad15f8b](unnamed_75afc12dd3fd43dd9cf4385d0ad15f8b.png)
![unnamed_0b70417e642c48bca70024b65956bd6a](unnamed_0b70417e642c48bca70024b65956bd6a.png)
![unnamed_af12ca1f07514f5ba354c2e8eaf7ba13](unnamed_af12ca1f07514f5ba354c2e8eaf7ba13.png)
![unnamed_8c0f4c5df2204163965bc2fb6103c6a4](unnamed_8c0f4c5df2204163965bc2fb6103c6a4.png)
