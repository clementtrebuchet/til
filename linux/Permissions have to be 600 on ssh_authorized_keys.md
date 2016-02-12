# Permissions have to be 600 on ~/.ssh/authorized_keys

If the file permissions on `~/.ssh/authorized_keys` are too permissive, `sshd` will just refuse to use it for authorizing users when they log in with a public key.  It's a security feature -- if the file is world-writable, anybody could put their public key there and log on as you.

Setting the permissions of this file to 600 usually gets around this issue, and prevents it from being visible to anybody except the current issue:

    chmod 600 ~/.ssh/authorized_keys

It is possible to disable this checking in the sshd config, but that's generally not a good idea.

([source](http://www.openssh.com/faq.html#3.14))