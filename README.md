# Hyper-V VM Migration

## CentOS
Sources:  
https://mangolassi.it/topic/8351/updating-the-linux-boot-image-before-migrating-from-vmware-to-hyper-v/10  
https://forums.centos.org/viewtopic.php?t=61699  

Antes de migrar, instalar os drivers do hyper-v
```bash

# CentOS 5 regenerate initrd for Hyper-V
mkinitrd -f -v --with=hid-base-hv --with=hid-hyperv --with=hv_utils --with=hv_vmbus --with=hv_storvsc --with=hv_netvsc /boot/initrd-$(uname -r).img $(uname -r)

# CentOS 6 regenerate initramfs for Hyper-V
mkinitrd -f -v --with=hid-base-hv --with=hid-hyperv --with=hv_utils --with=hv_vmbus --with=hv_storvsc --with=hv_netvsc /boot/initramfs-$(uname -r).img $(uname -r)

# CentOS 7 regenerate initramfs for Hyper-V
mkinitrd -f -v --with=hid-hyperv --with=hv_utils --with=hv_vmbus --with=hv_storvsc --with=hv_netvsc /boot/initramfs-$(uname -r).img $(uname -r)
```

CentOS 7
```bash
dracut -f --add-drivers "hv_vmbus hv_storvsc hv_netvsc hv_utils hv_balloon hyperv-keyboard hyperv_fb hid-hyperv"
```
