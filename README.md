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

License
-------

All third-party works are documented in `debian/copyright`, along with
their original author. Works which I authored are subject to the terms
of the Expat/MIT License.
