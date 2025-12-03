# 109.4 Configure client side DNS (weight: 2)

| **Weight**     | 2                                                                                                                       |
|----------------|:------------------------------------------------------------------------------------------------------------------------|
| **Description** | Candidates should be able to configure DNS on a client host. |

## Key Knowledge Areas:

- Query remote DNS servers.
- Configure local name resolution and use remote DNS servers.
- Modify the order in which name resolution is done.
- Debug errors related to name resolution.
- Awareness of systemd-resolved.

## The following is a partial list of the used files, terms and utilities:

- [/etc/hosts](#etc-hosts)
- [/etc/resolv.conf](#etc-resolv-conf)
- [/etc/nsswitch.conf](#etc-nsswitch-conf)
- [host](#host)
- [dig](#dig)
- [getent](#getent)
