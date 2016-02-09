# Disable time sync between a VirtualBox host and its guest

If you have the VirtualBox Guest Additions installed on your guest VM, the clock on the guest gets automatically synced to the clock of the host.

This is normally useful, but was causing us problems because we wanted to adjust the guest clock to test some function at "interesting" time intervals.  Any attempts to adjust the system clock in the guest were immediately reverted.

To disable this behaviour, use

    vboxmanage setextradata <vmname> "VBoxInternal/Devices/VMMDev/0/Config/GetHostTimeDisabled" "1"

replacing `<vmname>` with the name of your VM.

[source](http://rickguyer.com/virtualbox-disable-time-sync-between-host-and-client/)