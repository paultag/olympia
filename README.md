olympia
=======

These packages are a set of configuration defaults that tear up the default
Debian configuration in favor of the undocumented and maybe unexpected
configuration that Paul Tagliamonte enjoys.

As such, this is likely unusable for most of the population. That's OK,
you're normal.

Building
--------

```
$ dpkg-buildpackage -us -uc
$ sudo dpkg -i ../*.deb
```

Post-install
------------

PKCS11
------

If you've installed olympia-libpam-pkcs11, you should enable this carefully
after a bit of testing. Here's what you do:

 1. Open a shell with `sudo su`, and keep that open in case this goes wrong.
    I usually use a `tty`, so that testing the below isn't painful.
 1. In another shell, run `pklogin_finder`, and unsure the correct UID is
    shown on the screen.
 1. Run the command `sudo pam-auth-update`. Check `Olympia PKCS11 authentication`.
 1. Verify sudo works in yet another terminal.
 1. If it works and things are happy, you can now re-run `pam-auth-update` and
    disable `UNIX authentication`.
 1. Log out of GNOME and back in, using your PKCS11 token.
 1. Try it again without a token installed. It should fail.
 1. Reboot the machine and ensure it's working right. At this point you'll lose
    your root shell, and have to use a `d-i` rescue image to decrypt the drive
    and chroot.


License
-------

All third-party works are documented in `debian/copyright`, along with
their original author. Works which I authored are subject to the terms
of the Expat/MIT License.
