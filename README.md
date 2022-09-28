# VM-Mirror


Following repository are x86_64 VMs converted from other VM images into QCOW2 for usage with QEMU/[UTM](https://mac.getutm.app).

| VM | Source | Converted (ready to use) | Username/Password |
|:---|:---|:---| :--- |
| Metasploitable | [rapid7/metasploitable](https://information.rapid7.com/download-metasploitable-2017.html) | [Metasploitable.Emulation.utm.zip](https://github.com/khronokernel/VM-Mirror/releases/download/0.0.1/Metasploitable.Emulation.utm.zip) | msfadmin / msfadmin |
| Hacky Hack | hacky_hack.ova (ITSC200) | [Hacky.Hack.Emulation.utm.zip](https://github.com/khronokernel/VM-Mirror/releases/download/0.0.1/Hacky.Hack.Emulation.utm.zip) | |

Once downloaded, unzip them and import into [UTM](https://mac.getutm.app).

## Recreation

To recreate these VMs, you can use the following commands (note: above VMs are already converted and ready to use):

```sh
# VMDK (Metasploitable)
qemu-img convert -O qcow2 -c Metasploitable.vmdk Metasploitable.qcow2

# OVA (Hacky Hack)
tar -xvf hacky_hack.ova
qemu-img convert -O qcow2 -c hacky_hack-disk001.vmdk hacky_hack-disk001.qcow2
```

Once converted, install [UTM](https://mac.getutm.app) and create a new VM in emulation mode. Then add the newly generated QCOW2 file as an IDE disk in the VM's settings.
