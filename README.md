pmacct - modified
-----------------

This repository contains debian control files for creating an Ubuntu package for Trusty Tahr, and adds the following features to pmacct 1.5.0rc2:

* Fix implicit return type errors, this prevented the package from being built by Ubuntu PPA.
* Add persistent message support for the AMQP plugin.

Building
========

To build this package, I suggest using pbuilder-dist:

1. Download the [original tarball], and save it one directory higher as "pmacct_1.5.0~rc2.orig.tar.gz".
2. Install pbuilder: `apt-get install ubuntu-dev-tools debhelper`.
3. Create a pbuilder environment for Trusty Tahr: `pbuilder-dist trusty create`.
4. Create the source package and .dsc file: `make -f debian/Makefile source_no_sign`.
5. Create the package using pbuilder-dist:  `make -f debian/Makefile pbuild CHANGES=../pmacct_1.5.0~rc2-chaos5.dsc`.

OR

1. Install my PPA and install the package: `add-apt-repository ppa:lordgaav/pmacct && apt-get update && apt-get install pmacct`.

[original tarball]: http://www.pmacct.net/pmacct-1.5.0rc2.tar.gz
