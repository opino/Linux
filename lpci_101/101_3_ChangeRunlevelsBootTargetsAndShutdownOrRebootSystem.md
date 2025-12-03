# 101.3 Change Runlevels / Boot Targets and Shutdown or Reboot System (weight: 3)

| **Weight**     | 3                                                                                                                       |
|----------------|:------------------------------------------------------------------------------------------------------------------------|
| **Description** | Candidates should be able to manage the SysVinit runlevel or systemd boot target of the system. This objective includes changing to single user mode, shutdown or rebooting the system. Candidates should be able to alert users before switching runlevels / boot targets and properly terminate processes. This objective also includes setting the default SysVinit runlevel or systemd boot target. It also includes awareness of Upstart as an alternative to SysVinit or systemd. |

## Key Knowledge Areas:

- Set the default runlevel or boot target
- Change between runlevels / boot targets including single user mode
- Shutdown and reboot from the command line
- Alert users before switching runlevels / boot targets or other major system events
- Properly terminate processes
- Awareness of acpid

## The following is a partial list of the used files, terms and utilities:

- [/etc/inittab](#etcinittab)
- [shutdown](#shutdown)
- [init](#init)
- [/etc/init.d/](#etcinitd)
- [telinit](#telinit)
- [systemd](#systemd)
- [systemctl](#systemctl)
- [/etc/systemd/](#etcsystemd)
- [/usr/lib/systemd/](#usrlibsystemd)
- [wall](#wall)
