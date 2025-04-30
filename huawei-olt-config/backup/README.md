# Backup & Restore Guide

Use the following commands to backup and restore the configuration and data from Huawei MA56xx OLTs.

## Backup Commands

```bash
backup configuration tftp:10.11.104.5 backupconf.txt
backup data tftp:10.11.104.5 bakdata.dat
```

## Restore Commands

```bash
load configuration tftp:10.11.104.5 backupconf.txt all
load data tftp:10.11.104.5 bakdata.dat
active configuration system
```

## Notes

- Ensure a working TFTP server is reachable from the OLT.
- Use Ethernet cable between the OLT's main board and your laptop when using TFTP.
