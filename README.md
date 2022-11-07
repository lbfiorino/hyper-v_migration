# hyper-v_migration

## CentOS 7

Antes de migrar, instalar os drivers do hyper-v
```bash
dracut -f --add-drivers "hv_vmbus hv_storvsc hv_netvsc hv_utils hv_balloon hyperv-keyboard hyperv_fb hid-hyperv"
```
