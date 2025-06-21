80/tcp   open  http    Apache httpd 2.4.10 ((Debian))
|_http-title: Did not follow redirect to <http://dc-2/>
|_http-server-header: Apache/2.4.10 (Debian)



a wordpress site is running:




so i found out what the users are via wpscan 





i use cewl to generate a custom wordlist

cewl <http://dc-2>  -w password.out  

and i started bruteforcing :


and get two combinations



flag 1:



flag 2:



we dont have admin creeds thats why we cant exploit wordpress to get RCE 
but i tried these cresd on ssh 
and login as tom




and then i see that this is a restricted shell :
we have some commands to execute 




flag3.txt



flag4.txt






db creds have been found:





after a lot of harword and triel and error we escape from restricted shell:



my sql db 







we try jerry's password and login in and then sudo -l 


/us/bin/git    tried to go to gtfobins and got root




THE END![unnamed_eeeedc9b19f84500a9f7e98ab43c4319](unnamed_eeeedc9b19f84500a9f7e98ab43c4319.png)
![unnamed_f946258e2eaa45aa8d30edbce0d45ee3](unnamed_f946258e2eaa45aa8d30edbce0d45ee3.png)
![unnamed_03a7ba5b6d7449e7ab9c404447651869](unnamed_03a7ba5b6d7449e7ab9c404447651869.png)
![unnamed_dffde9350d8d464abbba3551b9587068](unnamed_dffde9350d8d464abbba3551b9587068.png)
![unnamed_4a6c0804f0af41cc9fa8ea93054e2932](unnamed_4a6c0804f0af41cc9fa8ea93054e2932.png)
![unnamed_975d7420696049de85cf41d8ffe94845](unnamed_975d7420696049de85cf41d8ffe94845.png)
![unnamed_a68712ad57db42d796e0db744e840c25](unnamed_a68712ad57db42d796e0db744e840c25.png)
![unnamed_7e34b2f2e52844f2b8033a9dd32d0b5d](unnamed_7e34b2f2e52844f2b8033a9dd32d0b5d.png)
![unnamed_837fd06f15a94427bbfbd4e2ab1ab615](unnamed_837fd06f15a94427bbfbd4e2ab1ab615.png)
![unnamed_5d7abbb7b35d42d09b79a9b1e6d42353](unnamed_5d7abbb7b35d42d09b79a9b1e6d42353.png)
![unnamed_c759c9a197144c5698ae0617f289b7c4](unnamed_c759c9a197144c5698ae0617f289b7c4.png)
![unnamed_c4322791e9f34e67ba58862579b9e9b0](unnamed_c4322791e9f34e67ba58862579b9e9b0.png)
![unnamed_ba821b5c8e594f62b243192dea8debe5](unnamed_ba821b5c8e594f62b243192dea8debe5.png)
![unnamed_06e381d86d4c4a69b1b40c441e500812](unnamed_06e381d86d4c4a69b1b40c441e500812.png)
