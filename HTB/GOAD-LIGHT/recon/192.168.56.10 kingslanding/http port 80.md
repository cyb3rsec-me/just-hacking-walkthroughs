nikto output :



- Nikto v2.5.0
---------------------------------------------------------------------------
+ Target IP:          192.168.56.10
+ Target Hostname:    192.168.56.10
+ Target Port:        80
+ Start Time:         2024-12-19 10:53:21 (GMT-5)
---------------------------------------------------------------------------
+ Server: Microsoft-IIS/10.0
+ /: Retrieved x-powered-by header: ASP.NET.
+ /: The anti-clickjacking X-Frame-Options header is not present. See: <https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-Frame-Options>
+ /: The X-Content-Type-Options header is not set. This could allow the user agent to render the content of the site in a different fashion to the MIME type. See: <https://www.netsparker.com/web-vulnerability-scanner/vulnerabilities/missing-content-type-header/>
+ /7eg3y4x0.asmx: Retrieved x-aspnet-version header: 4.0.30319.
+ No CGI Directories found (use '-C all' to force check all possible dirs)
+ OPTIONS: Allowed HTTP Methods: OPTIONS, TRACE, GET, HEAD, POST .
+ OPTIONS: Public HTTP Methods: OPTIONS, TRACE, GET, HEAD, POST .
+ 8254 requests: 0 error(s) and 6 item(s) reported on remote host
+ End Time:           2024-12-19 10:53:53 (GMT-5) (32 seconds)
---------------------------------------------------------------------------
+ 1 host(s) tested


s