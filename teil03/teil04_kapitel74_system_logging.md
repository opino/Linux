
# 108.2 System logging
Reference to LPI objectives
LPIC-1 v5, Exam 102, Objective 108.2 System logging

Weight
4

Description

Candidates should be able to configure rsyslog. This objective also includes configuring the logging daemon to send log output to a central log server or accept log output as a central log server. Use of the systemd journal subsystem is covered. Also, awareness of syslog and syslog-ng as alternative logging systems is included.


* Basic configuration of rsyslog.
* Understanding of standard facilities, priorities and actions.
* Query the systemd journal.
* Filter systemd journal data by criteria such as date, service or priority
* Configure persistent systemd journal storage and journal size
* Delete old systemd journal data
* Retrieve systemd journal data from a rescue system or file system copy
* Understand interaction of rsyslog with systemd-journald
* Configuration of logrotate.
* Awareness of syslog and syslog-ng.

The following is a partial list of the used files, terms and utilities:

* /etc/rsyslog.conf
* /var/log/
* logger
* logrotate
* /etc/logrotate.conf
* /etc/logrotate.d/
* journalctl
* systemd-cat
* /etc/systemd/journald.conf
* /var/log/journal/


# Prüfungsvorbereitung aus 2007 

* https://www.linux-magazin.de/ausgaben/2007/06/aufgepasst-und-ueberwacht/
