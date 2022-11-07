# hyper-v_migration

## CentOS

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
