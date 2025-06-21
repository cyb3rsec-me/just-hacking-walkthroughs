# HTB Forest - Red Team Lab

**Type:** Active Directory (Internal Lab)  
**Objective:** Domain Admin via AS-REP Roasting + DCSync  
**Report:** [Forest_Writeup.pdf](./Forest_Writeup.pdf)

### 🔹 Attack Chain:
1. Enum LDAP users
2. AS-REP Roasting → Cracked `svc-alfresco`
3. Evil-WinRM login
4. DCSync via Account Operators
5. PSExec → DA shell

### 💡 Skills Practiced:
- Kerberos exploitation
- Internal AD privilege escalation
- Realistic adversary simulation
