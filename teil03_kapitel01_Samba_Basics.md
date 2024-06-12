# Topic 301: Samba Basics

## 301.1 Samba Concepts and Architecture 
Weight 2

Candidates should understand the essential concepts of Samba, including the various Samba server processes and networking protocols used by Samba when acting in various roles. Samba version 4.8 or higher is covered.

Key Knowledge Areas:

* Understand the roles of the various Samba daemons and components
* Understand key issues regarding heterogeneous networks
* Understand the networking services used with SMB/CIFS and Active Directory, including their ports
* Understand the major features of SMB protocol versions 1.0, 2.0, 2.1 and 3.0
* Understand of Samba 3 and Samba 4 differences
* Awareness of Samba VFS modules
* Awareness of Samba Clustering and CTDB
  
Partial list of the used files, terms and utilities:

smbd, nmbd, samba, winbindd


## 301.2 Samba Configuration 
Weight 4

Candidates should be able to configure the Samba daemons.

Key Knowledge Areas:

* Manage Samba server file-based configuration
* Manage of Samba server registry-based configuration
* Manage of Samba configuration parameters and variables
* Understand Samba server roles and security modes
* Configure Samba to use TLS
* Check the validity of a Samba configuration
* Troubleshoot and debug configuration problems with Samba
* Understand Windows tools used to configure a Samba Server

The following is a partial list of the used files, terms and utilities:

* smb.conf
** security
** server role
** server string
** server services
** tls enabled
** tls keyfile
** tls certfile
** tls dh params file
** tls cafile
** config backend
** registry shares
** include
** vfs objects
* samba-regedit
* HKLM\Software\Samba\
* REG_SZ, REG_MULTI_SZ
* testparm
* net registry (including relevant subcommands)
* Microsoft RSAT Tools
* Microsoft MMC
* Microsoft ADSI Edit
* Microsoft LDP
* Microsoft Regedit
