this is just a wordpress site running ;




TECHS_STACK :





its a wordpress site : so we can use wpscan to enumerate more :

users :


webdeveloper




dir-indexing is allowed :



WP-includes





we did some dirbusting : but nothing interseting come out yet:

same goes for fuzzing :



we did :
dirbusting ✅️
vhosting  ✅️
source-code enum ✅️




after doiung some dir busting we found a dir :


it has  .cap file :



lets analyse this with wireshark:

in that pcap we found a password :


webdeveloper : Te5eQg&4sBS!Yr$)wf%(DcAd 



we successfully logs in :






i tried variuos things BUT ; 
then i upload a maliciiuos plugin and get a meterpreter shell:





we grab the mysql creds from : wp-config.php file : places in var/www/html



webdeveloper : MasterOfTheUniverse




and as i thought these creds were resused and we can login as ssh :




privilege escalation:

sudo -l : tells as what can we execute as a root user : or we can say what our user can execute as root privileges :




and we can exploit this to get our flag easily :




and i also got root by  writing : into /etc/sudoers file :





done 
![unnamed_b3ab943706964b3694243a9aa5c09b36](unnamed_b3ab943706964b3694243a9aa5c09b36.png)
![unnamed_70e1accdb5dc448db6128cf86c5c454f](unnamed_70e1accdb5dc448db6128cf86c5c454f.png)
![unnamed_5342ec0c371b4645ab21c3123cfe9333](unnamed_5342ec0c371b4645ab21c3123cfe9333.png)
![unnamed_bb23e81a04394356997371752488bbc3](unnamed_bb23e81a04394356997371752488bbc3.png)
![unnamed_eed07e5242694304b9c3edf91f74cd8b](unnamed_eed07e5242694304b9c3edf91f74cd8b.png)
![unnamed_17cdcbc214254b33933c2d234dc92f3b](unnamed_17cdcbc214254b33933c2d234dc92f3b.png)
![unnamed_b93e6244caef4713904514e23fcc98db](unnamed_b93e6244caef4713904514e23fcc98db.png)
![unnamed_20728d8237774e03b8e02afe6574c81f](unnamed_20728d8237774e03b8e02afe6574c81f.png)
![unnamed_9bb01a438caf47f9bdfa856c5d5a9b83](unnamed_9bb01a438caf47f9bdfa856c5d5a9b83.png)
![unnamed_8bbbb2e6b22841d7ace155597f8dd3e2](unnamed_8bbbb2e6b22841d7ace155597f8dd3e2.png)
![unnamed_c4269ee5a40840d48eeb5282ff96fe0b](unnamed_c4269ee5a40840d48eeb5282ff96fe0b.png)
![unnamed_48439f197a6949c59f1b5bcb53547127](unnamed_48439f197a6949c59f1b5bcb53547127.png)
![unnamed_22dd2b475682420392f7fbef24b134e3](unnamed_22dd2b475682420392f7fbef24b134e3.png)
![unnamed_c67c1b8080d44a9595d21a38422a7269](unnamed_c67c1b8080d44a9595d21a38422a7269.png)
![unnamed_7e512b0adeee4d8188a1cb643efa046d](unnamed_7e512b0adeee4d8188a1cb643efa046d.png)
