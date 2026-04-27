# Hardware-backed-disk-encryption-for-Ubuntu-26.04

Append in /etc/crypttab
```
dm_crypt-0 UUID=xxxxxxx-xxxx-xxxx-xxxx none luks,tpm2-device=auto,tpm2-pin=yes,tpm2-measure-pcr=yes,discard,no-read-workqueue,no-write-workqueue
```
