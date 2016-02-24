# How to create a symlink without ln – and generally get by with missing libraries

The popular Linux distros include [busybox](https://busybox.net/downloads/BusyBox.html), which is a statically-linked collection of Unix tools. Crucially, that means you only need the binary – if you’ve messed up your system libraries or deleted important components, it will still work.

For example, if you’d deleted the `/lib64/ld-linux-x86-64.so.2` symlink, which breaks pretty much all external binaries, you can restore the symlink as follows:

```console
$ /sbin/busybox ln -s /lib64/ld-2.12.so /lib64/ld-linux-lx86-64.so.2
```

Yes, this really happened to me.

(As a fun side effect, any attempts to SSH into the box will fail, because you can’t start a new shell.)

([source](http://serverfault.com/a/594351/206273))