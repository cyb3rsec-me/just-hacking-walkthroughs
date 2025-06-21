IP :  192.168.137.117


OS : Debian Linux 8


OPEN_PORTS:
80/tcp    open  http    syn-ack ttl 64
111/tcp   open  rpcbind syn-ack ttl 64
37215/tcp open  unknown syn-ack ttl 64


NMAP_OUTPUT:

80/tcp    open  http    nginx 1.6.2
|_http-title: Welcome
|_http-server-header: nginx/1.6.2
111/tcp   open  rpcbind 2-4 (RPC #100000)
| rpcinfo: 
|   program version    port/proto  service
|   100000  2,3,4        111/tcp   rpcbind
|   100000  2,3,4        111/udp   rpcbind
|   100000  3,4          111/tcp6  rpcbind
|   100000  3,4          111/udp6  rpcbind
|   100024  1          34565/udp   status
|   100024  1          37215/tcp   status
|   100024  1          50781/tcp6  status
|_  100024  1          55277/udp6  status
37215/tcp open  status  1 (RPC #100024)









