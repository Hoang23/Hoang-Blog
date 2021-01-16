---
title: "Home network"
subtitle: Setting up NAS and mini PC for home
summary:  Setting up NAS and mini PC for home
showDate: True
featured: false
draft: false
tags: ["hardware","linux","docker"]

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder. 
image:
  caption: ""
  focal_point: ""
---
<sub>January 14 2021</sub>

Recently I've been interested in preserving digital data such as photos and files as well as centralising my things into one place. As such I worked on a very small home setup consisting of an Intel Nuc and Synology NAS. 

The NAS is predominently used as a storage device that serves files allowing the other computers on the network to access data on the 4tb hard drives. A VPN server was setup using OpenVPN to overcome location restrictions when I am away from the network, allowing me to still access the network remotely. This makes it easy to access files, media and virtual machines from anywhere on any device including the NUC. 

VMware ESXi, an enterprise hypervisor similar to Proxmox is installed directly on the NUC. It currently runs multiple Linux virtual machines simultaneously such as a debian server for self hosting docker cotainers and ubuntu-desktop for development purposes.

<b> Setup and configurations </b>

Synology NAS - file system
- The NAS comes with its own Linux-based OS called DSM
- Raid 1 was used for the 2 hardrives therefore making one of them redundant
- NAS was given a static ip address. On my router I set a start and end ip address for DHCP therefore my devices will be assigned an IP between these addresses
- The NAS was given an address not between the range of the DHCP IP address pool to avoid an address conflict on my network if the router would give it to another DHCP client such as a client virtual machine

Intel NUC - Type 1 hypervisor
- VMware ESXi was installed as the acting OS. Nas was mounted through NFS in order to store the VMs on. 
- Debian and ubuntu-desktop virtual machines are accessed through ssh and both mount folders from the NAS through CIFS
- Some vms require a static ip. That can be done on the router or client, in this case it was configured on the client in /etc/network/interfaces
- Finally all the vms required same basic installations and configurations. The below script was ran on every install with "yes | sh script.sh"

<script src="https://gist.github.com/Hoang23/ea18dff05443b90fc2622350c8f6ec5d.js"></script>