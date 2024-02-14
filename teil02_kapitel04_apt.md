# Paketverwaltung mit apt  

## apt


* apt-get update downloads the package lists from the repositories and "updates" them to get information on the newest versions of packages and their dependencies. It will do this for all repositories and PPAs.
* apt-get upgrade will fetch new versions of packages existing on the machine if APT knows about these new versions by way of apt-get update.

 
```
apt update && apt upgrade
```


## dpkg 

```
dpkg --list | grep linux-images
``` 

```
dpkg --list | grep linux-header
``` 


### Bedeutung der Buchstaben von dpkg --list

First character: The possible value for the first character. The first character signifies the desired state, like we (or some user) is marking the package for installation

* u: Unknown (an unknown state)
* i: Install (marked for installation)
* r: Remove (marked for removal)
* p: Purge (marked for purging)
* h: Hold

Second Character: The second character signifies the current state, whether it is installed or not. The possible values are

* n: Not- The package is not installed
* i: Inst – The package is successfully installed
* c: Cfg-files – Configuration files are present
* u: Unpacked- The package is stilled unpacked
* f: Failed-cfg- Failed to remove configuration files
* h: Half-inst- The package is only partially installed
* W: trig-aWait
* t: Trig-pend
