 Current setup of the machine: 

 Hardware: \
 The machine is set within a Debian based hypervisor called Proxmox. 
 
 The allocated resources are: \
 OS -  VERSION="22.04.5 LTS (Jammy Jellyfish)" (Ubuntu server) \
 CPU - 2 cores(host type configured in terms of virtualization) \
 Memory - 6144MB \
 Disk - /dev/mapper/ubuntu--vg-ubuntu--lv   79G  5.6G   70G   8% /
 80GB mounted on the root folder. \
 Network - quemu guest agent installed. IP set to 192.168.0.10 outside DHCP range and reserved in the router. 

 Internal: \
 Users - labuser (sudoer) \
 Hostname - mentee (really creative by me I know :D) \
 View within dashboard - https://imgur.com/a/bsrRqYJ