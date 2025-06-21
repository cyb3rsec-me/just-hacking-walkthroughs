we are login as restricted shell :



only cat , env , ls are enable :

lets try to bypass this annoying restricted shell:


and we did it :

via this :

ssh mindy@192.168.101.58 -t "bash --noprofile"







post enumertaion :

users :


sudo -l : sudo not foundt


SUIDS :




james /home dir :





/opt :





there is a file tmp.py : and we can read that execute that or even have write permission :




nothing in : /var/www



lets run lpspy


and some files is running ;



okay we can do something about it :









/opt/tmp.py running as cronjob and we have rwx access to that file  so we can place our malicious file there
and can get root shell:

 



root.txt


![unnamed_77a387d9728d42878aa2cc9138529ef1](unnamed_77a387d9728d42878aa2cc9138529ef1.png)
![unnamed_5fdbe96430f349a3839617e286ef2efb](unnamed_5fdbe96430f349a3839617e286ef2efb.png)
![unnamed_2ae2b99e15d24c259e299938cf26aa3a](unnamed_2ae2b99e15d24c259e299938cf26aa3a.png)
![unnamed_72c271e13d864d8d8a9e6b97f17b6024](unnamed_72c271e13d864d8d8a9e6b97f17b6024.png)
![unnamed_95fe34b0fbfb4ae1bc739bca6cd42947](unnamed_95fe34b0fbfb4ae1bc739bca6cd42947.png)
![unnamed_4efc2ca34713498998adc916b5aff9c2](unnamed_4efc2ca34713498998adc916b5aff9c2.png)
![unnamed_b776d47f176141079aa968418e0c896f](unnamed_b776d47f176141079aa968418e0c896f.png)
![unnamed_4020dba3c2ae419588f4d872d48974e1](unnamed_4020dba3c2ae419588f4d872d48974e1.png)
![unnamed_dc352d2560cb48cba6ae4e993212d639](unnamed_dc352d2560cb48cba6ae4e993212d639.png)
![unnamed_130a31517e7944808cb1469f868a15a4](unnamed_130a31517e7944808cb1469f868a15a4.png)
![unnamed_e911f6fe7c554c0ab9d675847d4d65e4](unnamed_e911f6fe7c554c0ab9d675847d4d65e4.png)
![unnamed_3e61a146bb284814adade04b83b35cc8](unnamed_3e61a146bb284814adade04b83b35cc8.png)
![unnamed_087becb0193a43d082ff79aba3fe86ed](unnamed_087becb0193a43d082ff79aba3fe86ed.png)
