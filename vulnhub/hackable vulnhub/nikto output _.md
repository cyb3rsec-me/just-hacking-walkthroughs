- Nikto v2.5.0
---------------------------------------------------------------------------
+ Target IP:          192.168.254.177
+ Target Hostname:    192.168.254.177
+ Target Port:        80
+ Start Time:         2024-11-04 16:58:08 (GMT-5)
---------------------------------------------------------------------------
+ Server: Apache/2.4.46 (Ubuntu)
+ /: The anti-clickjacking X-Frame-Options header is not present. See: <https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/X-Frame-Options>
+ /: The X-Content-Type-Options header is not set. This could allow the user agent to render the content of the site in a different fashion to the MIME type. See: <https://www.netsparker.com/web-vulnerability-scanner/vulnerabilities/missing-content-type-header/>
+ No CGI Directories found (use '-C all' to force check all possible dirs)
+ /config/: Directory indexing found.
+ /robots.txt: Entry '/config/' is returned a non-forbidden or redirect HTTP code (200). See: <https://portswigger.net/kb/issues/00600600_robots-txt-file>
+ /robots.txt: contains 1 entry which should be manually viewed. See: <https://developer.mozilla.org/en-US/docs/Glossary/Robots.txt>
+ /: Server may leak inodes via ETags, header found with file /, inode: 447, size: 5c601c5628bac, mtime: gzip. See: <http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2003-1418>
+ Apache/2.4.46 appears to be outdated (current is at least Apache/2.4.54). Apache 2.2.34 is the EOL for the 2.x branch.
+ OPTIONS: Allowed HTTP Methods: GET, POST, OPTIONS, HEAD .
+ /config.php: PHP Config file may contain database IDs and passwords.
+ /config/: Configuration information may be available remotely.
+ /backup/: Directory indexing found.
+ /backup/: This might be interesting.
+ /css/: Directory indexing found.
+ /css/: This might be interesting.
+ /login.php: Admin login page/section found.
+ /login.php?-s: PHP allows retrieval of the source code via the -s parameter, and may allow command execution. See: <http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2012-1823>
+ 8103 requests: 0 error(s) and 16 item(s) reported on remote host
+ End Time:           2024-11-04 16:58:28 (GMT-5) (20 seconds)
---------------------------------------------------------------------------
+ 1 host(s) tested


