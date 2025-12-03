# 102.1 Design Hard Disk Layout (weight: 2)

| **Weight**     | 2                                                                                                                       |
|----------------|:------------------------------------------------------------------------------------------------------------------------|
| **Description** | Candidates should be able to design a disk partitioning scheme for a Linux system. |

## Key Knowledge Areas:

- Allocate filesystems and swap space to separate partitions or disks
- Tailor the design to the intended use of the system
- Ensure the `/boot` partition conforms to the hardware architecture requirements for booting
- Knowledge of basic features of LVM

## The following is a partial list of the used files, terms and utilities:

- [/ (root) filesystem](#rootfilesystem)
- [/var filesystem](#varfilesystem)
- [/home filesystem](#homefilesystem)
- [/boot filesystem](#bootfilesystem)
- [EFI System Partition (ESP)](#efisystempartition)
- [swap space](#swapspace)
- [mount points](#mountpoints)
- [partitions](#partitions)
