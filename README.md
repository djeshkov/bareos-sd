# Bareos Storage Daemon

* Port: `9103`
* Config: `/etc/bareos/bareos-sd.conf`
  A template gets copied if the file does not exists.

```
docker run \
  --rm \
  --name bareos-sd \
  -v /data/etc:/etc/bareos \
  -v /data/storage:/storage \
  -p 9103:9103 \
  --hostname bareos-sd \
  --link bareos-dir:bareos-dir \
  djeshkov/bareos-sd
```

### Adding more devices

TODO

### CIFS/SSHFS Mount
For cifs or sshfs mounts you need some more rights:
```
docker run ... --cap-add SYS_ADMIN --cap-add DAC_READ_SEARCH ...
```
