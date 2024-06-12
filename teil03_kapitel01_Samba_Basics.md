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

## 301.3 Regular Samba Maintenance
Weight 2

Candidates should know the various tools and utilities that are part of a Samba installation.

Key Knowledge Areas:

* Start and stop Samba services on domain controllers and file servers
* Monitor and interact with running Samba daemons
* Backup and restore TDB files
* Backup and restore an Active Directory domain controller
* Understand backup and recovery strategies for Active Directory domain controllers
* Understand the impact of virtualization on Active Directory domain controllers

The following is a partial list of the used files, terms and utilities:

* systemctl
* smbcontrol (including relevant message types)
* smbstatus
* tdbbackup
* tdbrestore
* samba-tool domain backup (including subcommands)
* Virtual Machine Generation Identifier
* Virtual Machine Snapshots

301.4 Troubleshooting Samba
Weight 3

Candidates should be able to analyze and troubleshoot Samba issues. This includes accessing and modifying the LDAP content of a Samba server hosting an Active directory as well as working with trivial database files. Furthermore, candidates should be able to create a renamed clone of an existing Active Directory for debugging.

Key Knowledge Areas:

* Configure Samba logging, including setting log levels for specific debug classes and client-specific logging
* Query and modify the Samba password database
* Understand the contents of important TDB files
* List and edit TDB file content
* Identify TDB file corruption
* Access and modify objects in a Samba LDAP directory
* Enable and use the LDAP recycle bin
* Confirm the integrity of a domain controller’s database
* Create a renamed clone of a domain controller
* Awareness of Samba eventlog shipping
* Use rpcclient to query information on a Samba server

The following is a partial list of the used files, terms and utilities:

* smb.conf:
** log level
** debuglevel
* /var/log/samba/
* smbpasswd
* pdbedit
* registry.tdb
* secrets.tdb
* tdbdump
* tdbtool
* ldbsearch
* ldbmodify
* ldbedit
* ldbadd 
* ldbdel
* LDIF
* samba-tool dbcheck
* samba-tool domain backup (including relevant subcommands)
* rpcclient




