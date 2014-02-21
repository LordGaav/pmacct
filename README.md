pmacct - modified
-----------------

This repository contains debian control files for creating an Ubuntu package for Trusty Tahr. This package is based upon the current CVS snapshot,
and adds the following new features since 1.5.0rc2:

* Add persistent message support for the AMQP plugin.

Building
========

To build this package, I suggest using pbuilder-dist:

1. CVS checkout the current source, in a folder called pmacct-cvs, and create a tarball from it one directory higher as "pmacct_1.5.0~cvs.orig.tar.gz". Alternatively, download a prepared [CVS tarball] from me.
2. Install pbuilder: `apt-get install ubuntu-dev-tools debhelper`.
3. Create a pbuilder environment for Trusty Tahr: `pbuilder-dist trusty create`.
4. Create the source package and .dsc file: `make -f debian/Makefile source_no_sign`.
5. Create the package using pbuilder-dist:  `make -f debian/Makefile pbuild CHANGES=../pmacct_1.5.0XXXXX.dsc`.

OR

1. Install my PPA and install the package: `add-apt-repository ppa:lordgaav/pmacct && apt-get update && apt-get install pmacct`.

[CVS tarball]: https://www.dropbox.com/s/metw6ebu0b4abiz/pmacct_1.5.0cvs.orig.tar.gz
