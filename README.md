# VMware
<h1>Practical office work on EXSI Server of VNKN01</h1> <br>
<h2>VMware import and export OVA or OVF</h2> <br>
OVA (Open Virtual Appliance) - a single file used for import and export purposes.<br>
OVF (Open Virtualization Format) - Consists of three files with extensions .mf,.ovf and .vmdk<br><br>

![ovf](https://github.com/VNKN01/VMware/assets/44769452/7a06aaed-a90d-44dd-b19f-28e9687efb88)
<h3> Step-1 </h3> Find and Download the (VMware-ovftool-4.6.0-21452615-win.x86_64.exe) which is available to download in this repo
<h3> Step-2 </h3> list the VM which are available in EXSI Server type ovftool.exe vi://192.168.62.53/micostack <br>
<h3> Step-3 </h3>ovftool.exe vi://192.168.62.53/micostack "F:\Ubuntu Server Minimal installation ova\ubuntu-24.04-live-server-amd64.ova"<br>
