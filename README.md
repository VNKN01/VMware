# VMware
<h1>Practical office work on EXSI Server of VNKN01</h1> <br>
<h2>VMware import and export OVA or OVF</h2> <br>
OVA (Open Virtual Appliance) - a single file used for import and export purposes.<br>
OVF (Open Virtualization Format) - Consists of three files with extensions .mf,.ovf and .vmdk<br><br>

![ovf](https://github.com/VNKN01/VMware/assets/44769452/7a06aaed-a90d-44dd-b19f-28e9687efb88) <br><br>

<h2>Frist Export OVA Flile with Two Commands</h2> <br>

<h3> Step-1 </h3> Find and Download the (VMware-ovftool-4.6.0-21452615-win.x86_64.exe) which is available to download in this repo
<h3> Step-2 </h3> list the VM which are available in EXSI Server type <b>ovftool.exe vi://192.168.62.53/micostack</b> <br>
<h3> Step-3 </h3><b>ovftool.exe vi://192.168.62.53/micostack "F:\Ubuntu Server Minimal installation ova\ubuntu-24.04-live-server-amd64.ova"</b><br></br>

![2](https://github.com/VNKN01/VMware/assets/44769452/c20b4808-0dd0-48d3-8baa-4dce2bdbcb4f)

<h2>Frist OVA Flile into ESXI server with single Commands</h2> <br>

<b>ovftool.exe -ds="Windows Update" -dm=thin -n=Ubuntu-Kubernetes "G:\ubuntu\ubuntu-24.04-live-server-amd64.ova" vi://192.168.62.53</b> </b><br></br>

![2](https://github.com/VNKN01/VMware/assets/44769452/ab86fd0a-63b3-494b-ae06-1a0dcc0e0833)

<h4>Note: </h4>
We only need to change the file extension for exporting and importing.OVA to.OVF. This simple adjustment triggers the automatic creation of three files. For instance,<b>ovftool.exe vi://192.168.62.53/micostack "F:\Ubuntu Server Minimal installation ovf\ubuntu-24.04-live-server-amd64.ovf"</b>
https://youtu.be/QFyCF1b6BwI
