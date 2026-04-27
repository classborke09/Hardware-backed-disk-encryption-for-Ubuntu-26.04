# Hardware-backed-disk-encryption-for-Ubuntu-26.04

* Append in /etc/crypttab
```
dm_crypt-0 UUID=xxxxxxx-xxxx-xxxx-xxxx none luks,tpm2-device=auto,tpm2-pin=yes,tpm2-measure-pcr=yes,discard,no-read-workqueue,no-write-workqueue
```

* Edit Dracut
```
echo -e 'hostonly="yes"\nadd_dracutmodules+=" tpm2-tss "' >> /etc/dracut.conf.d/tpm2.conf
```

* Sign key into TPM module
```
sudo systemd-cryptenroll --tpm2-device=auto --tpm2-pcrs=7 /dev/disk/by-uuid/xxxxxxxx-xxxx-xxxx-xxxxx
``` 
