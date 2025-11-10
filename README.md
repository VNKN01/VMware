# VMware OVF Tool Usage Guide (Source/Destination Remain Same MAC Address)

[![VMware OVF Tool](https://img.shields.io/badge/VMware-OVF_Tool-blue)](https://www.vmware.com/support/developer/ovf/)

This guide explains how to **export** and **import** virtual machines (VMs) between ESXi hosts using the **VMware OVF Tool**, while keeping the MAC address the same.

---

## Table of Contents

- [Step 1: Download and Install VMware OVF Tool](https://developer.broadcom.com/tools/open-virtualization-format-ovf-tool/latest)
- [Step 2: Export VM from Source ESXi Host](#step-2-export-vm-from-source-esxi-host)  
- [Step 3: Import VM into Destination ESXi Host](#step-3-import-vm-into-destination-esxi-host)  
- YouTube Link: https://youtu.be/b754FYKwFJ8
- Author: SYED HAMMAD AHMED  

---

## Step 1: Install VMware OVF Tool

After installing VMware OVF Tool, navigate to its installation directory:

```bash
cd "C:\Program Files\VMware\VMware OVF Tool"

```

# VMware OVF Tool Usage Guide (Source/Destination Remain Same MAC Address)

This guide explains how to **export** and **import** virtual machines (VMs) between ESXi hosts using the **VMware OVF Tool**, while keeping the MAC address the same.

---



## Step 2: Export VM from ESXi Host (Source: 192.168.62.56)

Export the virtual machine **VNKN01-exam-01** to an `.OVA` file:

```bash

ovftool.exe --allowAllExtraConfig vi://root@192.168.62.56/VNKN01-exam-01 "H:\VNKN01-VMs-Backup\VNKN01-EXAM-01.OVA"
```
---

## Step 3: Import VM into ESXi Host (Destination: 192.168.62.55)

Import the exported `.OVA` file into the new ESXi host, power it on automatically, overwrite if it exists, and keep the MAC address:

```bash

ovftool.exe --allowAllExtraConfig --powerOn --overwrite -ds="DS-VNKN01" -dm=thin -n=VNKN01-EXAM-01 "H:\VNKN01-VMs-Backup\VNKN01-EXAM-01.ova" vi://192.168.62.55

```
---

## Notes

- `--allowAllExtraConfig` → Include all extra configurations.  
- `--powerOn` → Power on the VM automatically after import.  
- `--overwrite` → Replace an existing VM with the same name.  
- `-dm=thin` → Use thin provisioning for disks.  

# VMware
# VMware OVF Tool Usage Guide (Source/Destination are different MAC Addresses)
<h2>VMware import and export OVA or OVF</h2> <br>
OVA (Open Virtual Appliance) - a single file used for import and export purposes.<br>
OVF (Open Virtualization Format) - Consists of three files with extensions .mf,.ovf and .vmdk<br><br>

![ovf](https://github.com/VNKN01/VMware/assets/44769452/7a06aaed-a90d-44dd-b19f-28e9687efb88) <br><br>

<h2>Frist Export OVA Flile with Two Commands</h2> <br>

<h3> Step-1 </h3> Find and Download the (VMware-ovftool-4.6.0-21452615-win.x86_64.exe) which is available to download in this repo
<h3> Step-2 </h3> list the VM which are available in EXSI Server type <b>ovftool.exe vi://192.168.62.53/micostack</b> <br>
<h3> Step-3 </h3><b>ovftool.exe vi://192.168.62.53/micostack "F:\Ubuntu Server Minimal installation ova\ubuntu-24.04-live-server-amd64.ova"</b><br></br>

![2](https://github.com/VNKN01/VMware/assets/44769452/c20b4808-0dd0-48d3-8baa-4dce2bdbcb4f)

<h2>Scond OVA Flile Import into ESXI server with single Commands</h2> <br>

<b>ovftool.exe -ds="Windows Update" -dm=thin -n=Ubuntu-Kubernetes "G:\ubuntu\ubuntu-24.04-live-server-amd64.ova" vi://192.168.62.53</b> </b><br></br>

![2](https://github.com/VNKN01/VMware/assets/44769452/ab86fd0a-63b3-494b-ae06-1a0dcc0e0833)

<h4>Note: </h4>
We only need to change the file extension for exporting and importing.OVA to.OVF. This simple adjustment triggers the automatic creation of three files. For instance,<b>ovftool.exe vi://192.168.62.53/micostack "F:\Ubuntu Server Minimal installation ovf\ubuntu-24.04-live-server-amd64.ovf"</b>
https://youtu.be/QFyCF1b6BwI


