# Get a list of current filesystem mounts

Created some mounts, and forgotten where they are?

Run the `mount` command to find out:

```console
$ mount
/dev/xvda on / type ext4 (rw,noatime,errors=remount-ro)
proc on /proc type proc (rw)
none on /proc/sys/fs/binfmt_misc type binfmt_misc (rw,noexec,nosuid,nodev)
sysfs on /sys type sysfs (rw,noexec,nosuid,nodev)
...
```

