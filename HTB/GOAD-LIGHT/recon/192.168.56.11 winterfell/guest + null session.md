null + guest access not allowed :




┌──(kali㉿kali)-[~]
└─$ crackmapexec smb 192.168.56.11 -u '' -p ''  --shares

SMB         192.168.56.11   445    WINTERFELL       [*] Windows 10 / Server 2019 Build 17763 x64 (name:WINTERFELL) (domain:north.sevenkingdoms.local) (signing:True) (SMBv1:False)
SMB         192.168.56.11   445    WINTERFELL       [+] north.sevenkingdoms.local\: 
SMB         192.168.56.11   445    WINTERFELL       [-] Error enumerating shares: STATUS_ACCESS_DENIED
                                                                                                                                                                      
└─$ crackmapexec smb 192.168.56.11 -u 'guest' -p 'guest'  --shares


SMB         192.168.56.11   445    WINTERFELL       [*] Windows 10 / Server 2019 Build 17763 x64 (name:WINTERFELL) (domain:north.sevenkingdoms.local) (signing:True) (SMBv1:False)
SMB         192.168.56.11   445    WINTERFELL       [-] north.sevenkingdoms.local\guest:guest STATUS_LOGON_FAILURE 
                                                                                                                                                                      
┌──(kali㉿kali)-[~]
└─$ crackmapexec smb 192.168.56.11 -u 'guest' -p ''  --shares 

SMB         192.168.56.11   445    WINTERFELL       [*] Windows 10 / Server 2019 Build 17763 x64 (name:WINTERFELL) (domain:north.sevenkingdoms.local) (signing:True) (SMBv1:False)
SMB         192.168.56.11   445    WINTERFELL       [-] north.sevenkingdoms.local\guest: STATUS_ACCOUNT_DISABLED 
                                                                                                                 
                                                                                                                 
                                                                                                                 
                                                                                                                 