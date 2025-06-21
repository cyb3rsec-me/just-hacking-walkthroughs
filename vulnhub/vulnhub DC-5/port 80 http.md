to-dolist:  


1. dirbuster
2. vhosting
3. source code enum
4. hunt for params and links via b-suite 


dirbusting:
we found some of them:




tech_stack used :


a website with nginx :



vhosting :
dont have any vhosts:


source code has nothing but usual stuff:

---------






we have a contact page with some inputs :



lets fire up b-suite and test this:

i try some else :




we have rce via nginx log poisioning:




getting a reverse shell:
step 1. findinig nc 



step 2: reverse shell:via nc 








privilege escalation:
![unnamed_e282addf825242e7ae74072d10a7f93a](unnamed_e282addf825242e7ae74072d10a7f93a.png)
![unnamed_f7e0f8ff2abe49edb6ace73570365a63](unnamed_f7e0f8ff2abe49edb6ace73570365a63.png)
![unnamed_c362011baae24907af56d63e82586c49](unnamed_c362011baae24907af56d63e82586c49.png)
![unnamed_2321a91744ce48268e398a44fd748f59](unnamed_2321a91744ce48268e398a44fd748f59.png)
![unnamed_f39adbb104b3439db72bb2b8e03fa012](unnamed_f39adbb104b3439db72bb2b8e03fa012.png)
![unnamed_066c0713111845abab1acc09840ca98e](unnamed_066c0713111845abab1acc09840ca98e.png)
![unnamed_a485a43cfe764d618b088a09d9bbd123](unnamed_a485a43cfe764d618b088a09d9bbd123.png)
![unnamed_bf0e1de40d144d0bb6c83828b369498b](unnamed_bf0e1de40d144d0bb6c83828b369498b.png)
![unnamed_cc45d28dc8244fc9afe51fb5b35d72a0](unnamed_cc45d28dc8244fc9afe51fb5b35d72a0.png)
![unnamed_8793df5823a14c65abd85b5dff4510eb](unnamed_8793df5823a14c65abd85b5dff4510eb.png)
