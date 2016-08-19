# Bareos Storage Daemon

* Port: `9103`
* Config: `/etc/bareos/bareos-sd.conf`
  A template gets copied if the file does not exists.

```
docker run \
  --rm \
  --name bareos-sd \
  -v /opt/bareos/conf:/etc/bareos \
  -v /opt/backup-storage:/storage \
  --hostname bareos-sd \
  --link bareos-dir:bareos-dir \
  shoifele/bareos-sd
```

### CIFS/SSHFS Mount
For cifs or sshfs mounts you need some more rights:
```
docker run ... --cap-add SYS_ADMIN --cap-add DAC_READ_SEARCH ...
```
