# GPON Configuration Guide

This section provides configuration commands for GPON profiles and ONU authentication.

## Display OLT and ONU

```bash
display board 0
display ont autofind all
```

## VLAN Profile Configuration

```bash
ont-srvprofile gpon profile-id 2014 profile-name "2014"
ont-port pots adaptive eth adaptive
port vlan eth 1 translation 2014 user-vlan 2014
commit
quit
```

## Line Profile Configuration

```bash
ont-lineprofile gpon profile-id 2014 profile-name "2014"
tcont 1 dba-profile-id 100
gem add 1 eth tcont 1
gem mapping 1 1 vlan 2014
commit
quit
```

## ONU Authentication (SN Method)

```bash
ont add 0 sn-auth 4244434D62D7BD84 omci ont-lineprofile-id 1064 ont-srvprofile-id 1064 desc Test
ont port native-vlan 0 0 eth 1 vlan 1064
service-port vlan 1064 gpon 0/15/0 ont 0 gemport 1 multi-service user-vlan 1064
```

## Check Optical Info

```bash
display ont optical-info 0 1
```

## Find ONU by MAC

```bash
display ont info by-mac 00D1-9A01-03E7
```

## Delete ONU

```bash
display service-port port 0/1/0 ont 1
undo service-port 2
interface gpon 0/15
ont delete 0 0
```
