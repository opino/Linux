# 108.1 Maintain system time (weight: 3)

| **Weight**     | 3                                                                                                                       |
|----------------|:------------------------------------------------------------------------------------------------------------------------|
| **Description** | Candidates should be able to properly maintain the system time and synchronize the clock via NTP. |

## Key Knowledge Areas:

- Set the system date and time.
- Set the hardware clock to the correct time in UTC.
- Configure the correct timezone.
- Basic NTP configuration using ntpd and chrony.
- Knowledge of using the pool.ntp.org service.
- Awareness of the ntpq command.

## The following is a partial list of the used files, terms and utilities:

- [/usr/share/zoneinfo/](#usr-share-zoneinfo)
- [/etc/timezone](#etc-timezone)
- [/etc/localtime](#etc-localtime)
- [/etc/ntp.conf](#etc-ntp-conf)
- [/etc/chrony.conf](#etc-chrony-conf)
- [date](#date)
- [hwclock](#hwclock)
- [timedatectl](#timedatectl)
- [ntpd](#ntpd)
- [ntpdate](#ntpdate)
- [chronyc](#chronyc)
- [pool.ntp.org](#poolntp-org)
