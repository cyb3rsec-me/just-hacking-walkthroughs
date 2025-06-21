to do :

source code enum
dir busting
vhosting
param find via burp & scan with it




so we can't access any files on a nginx server so i tried to access it by ::::   squid proxy runnnig on 31337





curl   <http:///127.0.0.1:8080>  -x 192.168.241.28:31337


we can see there is file server running on localhost





i did some dirbusting :


and found a dir called :





littlesecrets-main




there is admin login pannel but how we access it :




I setup the proxy setting on foxy proxy :



so lets perform sql injection :


it is vulnerable to timebased sql injection 




pinky : f543dbfeaf238729831a321c7a68bee4

pinkymanage : 3pinkysaf33pinkysaf3

 

![unnamed_a938c57d426e49c2af8caaac3c837225](unnamed_a938c57d426e49c2af8caaac3c837225.png)
![unnamed_3209da1dbd99438b8d4a4e4c511a71ab](unnamed_3209da1dbd99438b8d4a4e4c511a71ab.png)
![unnamed_9e4c4d94862d4d84ae742cb3e3f50f75](unnamed_9e4c4d94862d4d84ae742cb3e3f50f75.png)
![unnamed_126baf9d517f4929bfa8bbed6cc538bb](unnamed_126baf9d517f4929bfa8bbed6cc538bb.png)
![unnamed_b042cc5a4a8346d897bf07874d56b006](unnamed_b042cc5a4a8346d897bf07874d56b006.png)
![unnamed_448e343359324a7b9b2fe0e0fc34b496](unnamed_448e343359324a7b9b2fe0e0fc34b496.png)
