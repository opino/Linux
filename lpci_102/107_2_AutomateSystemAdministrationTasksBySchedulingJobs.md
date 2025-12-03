# 107.2 Automate system administration tasks by scheduling jobs (weight: 4)

| **Weight**     | 4                                                                                                                       |
|----------------|:------------------------------------------------------------------------------------------------------------------------|
| **Description** | Candidates should be able to use cron and systemd timers to run jobs at regular intervals and to use at to run jobs at a specific time. |

## Key Knowledge Areas:

- Manage cron and at jobs.
- Configure user access to cron and at services.
- Understand systemd timer units.

## The following is a partial list of the used files, terms and utilities:

- [/etc/cron.{d,daily,hourly,monthly,weekly}/](#etc-cron-d-daily-hourly-monthly-weekly)
- [/etc/at.deny](#etc-at-deny)
- [/etc/at.allow](#etc-at-allow)
- [/etc/crontab](#etc-crontab)
- [/etc/cron.allow](#etc-cron-allow)
- [/etc/cron.deny](#etc-cron-deny)
- [/var/spool/cron/](#var-spool-cron)
- [crontab](#crontab)
- [at](#at)
- [atq](#atq)
- [atrm](#atrm)
- [systemctl](#systemctl)
- [systemd-run](#systemd-run)
