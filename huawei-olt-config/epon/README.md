# EPON Configuration Guide

This section provides configuration commands for EPON profiles and ONU authentication.

## VLAN Profile Configuration

```bash
ont-srvprofile epon profile-id 1064 profile-name 1064
ont-port pots adaptive eth adaptive
port vlan eth 1 1064
commit
quit
```

## Line Profile Configuration

```bash
ont-lineprofile epon profile-id 1064 profile-name 1064
llid dba-profile-id 50
commit
quit
```

## ONU Authentication (MAC Method)

```bash
ont add 0 mac-auth 00D1-9A01-03E7 oam ont-lineprofile-id 500 ont-srvprofile-id 500
ont port native-vlan 0 1 eth 1 vlan 500
service-port vlan 500 epon 0/1/0 ont 1 multi-service user-vlan 500
```

## Show Information

```bash
interface epon 0/1
display ont info 0 0
display current-configuration port 0/1/0
```
