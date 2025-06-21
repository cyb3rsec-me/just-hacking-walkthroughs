80/tcp open  http    Apache httpd 2.4.25 ((Debian))
|_http-title: Did not follow redirect to <http://wordy/>
|_http-server-header: Apache/2.4.25 (Debian)




add : <http://wordy> into /etc/hosts



its a wordpress site:



tech_stack used:




to-do list:
1.	dir busting
2. vhosting
3. source code enunm
4. expore with burp sute


1. dir busting:













2. users: find via wpscan



ok then i tried to brute force all of them byusing a hint i get from machines description:





mark : helpdesk01


then i enumerate website via wpscan and i found a vuln plugin is installed :



is vuln to and rce :



and lets fireup msfconsole and see it is expliotaible or not.



we get an rce :


db creds:



wpdbuser : meErKatZ

some stuff found in mark's dir:


graham : GSo7isUM1D4

has rights to run this file :


it is creating a backup of /var/ww/html




i see the permissions of the file backups.sh  is belongs to devs group 




my user graham is also belongs to devs group that means we can edit this file;




lets gets a shell as jens







okay : 


jens can execute nmap as root :


lets get root shell:

nmap doesn't have ineteractive option means its a new patched binary :

but we have a new methods also :



step 1 : create an env variable name :   TF=$(mktemp)
step2: write script into TF var  :  echo ‘os.execute("/bin/bash")’ > $TF
step3 :  execute thst script as nmap script:   sudo nmap --script=$TF



THE END 









![unnamed_daa6a6c7cd484853b2d2c73c43b9d646](unnamed_daa6a6c7cd484853b2d2c73c43b9d646.png)
![unnamed_ee98412402504c40939ef68d86722b56](unnamed_ee98412402504c40939ef68d86722b56.png)
![unnamed_3f8981a47e764a0e8387e20bce303e7c](unnamed_3f8981a47e764a0e8387e20bce303e7c.png)
![unnamed_4165d1e2f8214e5587d8a87b7d8e3a6d](unnamed_4165d1e2f8214e5587d8a87b7d8e3a6d.png)
![unnamed_5ba3aca8f4f24fd1a382708c226fd25b](unnamed_5ba3aca8f4f24fd1a382708c226fd25b.png)
![unnamed_1c3f97e7811e4715832e85b906f77fe4](unnamed_1c3f97e7811e4715832e85b906f77fe4.png)
![unnamed_907deb899b714f3d810cf5b558ae8cc3](unnamed_907deb899b714f3d810cf5b558ae8cc3.png)
![unnamed_b4e1c3a644ed48c6a71bb3608dc8d905](unnamed_b4e1c3a644ed48c6a71bb3608dc8d905.png)
![unnamed_7aa3727e13d84d139233b58cff3c3f23](unnamed_7aa3727e13d84d139233b58cff3c3f23.png)
![unnamed_bdfbc1fa253e46d8ae55fac1dfe95e16](unnamed_bdfbc1fa253e46d8ae55fac1dfe95e16.png)
![unnamed_bacf223dccc34dd7a8ba011a190b6c61](unnamed_bacf223dccc34dd7a8ba011a190b6c61.png)
![unnamed_2343ca424b8e490aa92f51a4fcc54c6b](unnamed_2343ca424b8e490aa92f51a4fcc54c6b.png)
![unnamed_72cbd9d5b2ad4e95b95ef739451a8805](unnamed_72cbd9d5b2ad4e95b95ef739451a8805.png)
![unnamed_f9616aea053c410db90c8d49aef21248](unnamed_f9616aea053c410db90c8d49aef21248.png)
![unnamed_dcc3fa256cac4d869d172284dbe99114](unnamed_dcc3fa256cac4d869d172284dbe99114.png)
![unnamed_34971f8fd47244e581675be9f3210ecf](unnamed_34971f8fd47244e581675be9f3210ecf.png)
![unnamed_c0ff708112324d4785d2441bcdefa917](unnamed_c0ff708112324d4785d2441bcdefa917.png)
![unnamed_c1c99d3ad0c54adb9073fe47310ccbe4](unnamed_c1c99d3ad0c54adb9073fe47310ccbe4.png)
![unnamed_4923982090954a62bbf6e37f10edad23](unnamed_4923982090954a62bbf6e37f10edad23.png)
![unnamed_51ee85c554444c6597d3d40702c97317](unnamed_51ee85c554444c6597d3d40702c97317.png)
