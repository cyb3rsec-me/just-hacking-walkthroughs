i got ssh access or initial foothold:


in janitor home we found a hidden dir and some passwds in it :



i use these passwd to again brute force : i found one extra:



i login  as fredf and fredf user has right to exeute a file as root :




so when i execute this : 

this showsa a python file test.py 

which only read from a file and appand into a file :




so i read /etc/shadow and write it into simple file : 

i get all passwd hashes :



lets try to crack the root hash:

okay 2nd approach :

we have a write capanbility as root : we can add another user who has use3r id of 1 in /etc/passwd and then login as that user :

step 1: create a user : passwd in linux format :

habi:$1$/UTMXpPC$Wrv6PM4eRHhB1/m1P.t9l.:0:0:siren:/home/habi:/bin/bash  : ilovehacking 

then save this into a file : > pass


step 2: write file pass into /etc/passwd :



step 3; login as that user :


and i am root :









![unnamed_95ebceaffd124759a8d18656ea27511e](unnamed_95ebceaffd124759a8d18656ea27511e.png)
![unnamed_249a70c3f9234424ac01f99f974e282b](unnamed_249a70c3f9234424ac01f99f974e282b.png)
![unnamed_eef8e9884e794c2daa48f856345ca6c4](unnamed_eef8e9884e794c2daa48f856345ca6c4.png)
![unnamed_77694c2b78da4385baab1d44b2e3fcaa](unnamed_77694c2b78da4385baab1d44b2e3fcaa.png)
![unnamed_ca07b9220ebd482b93d744689c887f7d](unnamed_ca07b9220ebd482b93d744689c887f7d.png)
![unnamed_ad4c56da6fb04cce8bcf0c9f8e1b804a](unnamed_ad4c56da6fb04cce8bcf0c9f8e1b804a.png)
![unnamed_82bf8b6e9d8343d8bd0f1c47470f2f2f](unnamed_82bf8b6e9d8343d8bd0f1c47470f2f2f.png)
![unnamed_45c7e3fca64248109f11dd29973bf5fe](unnamed_45c7e3fca64248109f11dd29973bf5fe.png)
![unnamed_c4be9b1b020549069467f9eb480ac561](unnamed_c4be9b1b020549069467f9eb480ac561.png)
![unnamed_61381dac439b4dd9b2602f82a252d0c8](unnamed_61381dac439b4dd9b2602f82a252d0c8.png)
