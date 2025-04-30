# Huawei MA56xx OLT Configuration Guide

This repository contains organized configuration commands and documentation for managing Huawei MA56xx series OLTs, including GPON and EPON settings, ONU provisioning, backup/restore procedures, and diagnostics.

- GPON Configuration
- EPON Configuration
- Backup & Restore

## Folder Structure

```
├── gpon/
│   └── README.md
├── epon/
│   └── README.md
├── backup/
│   └── README.md
└── README.md
```
## 📘 Configuration Categories

🔹 GPON

Configuration profiles, ONU authentication methods, VLAN tagging, and command references for GPON.

🔹 EPON

Includes service and line profile setup, MAC authentication, VLAN mapping, and monitoring commands for EPON.

🔹 Backup & Restore

Procedures for backing up and restoring Huawei OLT configurations and database via TFTP.

Each directory contains configurations and command references for the specific feature or protocol.


## ✅ Useful Commands
## Show Registered and Unregistered ONUs
```
display board 0
display ont autofind all
```
## Find ONU by MAC
```
display ont info by-mac 00D1-9A01-03E7
```
## ONU Laser Diagnostics
```
interface gpon 0/15
display ont optical-info 0 1
```
## ℹ️ Monitoring
```
display current-configuration port 0/1/0
display ont info 0 0
```

## ✍️ Author

Md Shoriful Islam

## 📄 License

This project is released under the MIT License.
