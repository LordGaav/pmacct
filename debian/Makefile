KEY=CD9C0E84
DIST=trusty
TARBALL=../pmacct_1.5.0~rc2.orig.tar.gz
SRCROOT=pmacct-1.5.0rc2

package:
	dpkg-buildpackage -A -us -uc
 
source:
	dpkg-buildpackage -S -k$(KEY)

source_no_sign:
	dpkg-buildpackage -S -us -d
 
upload_to_ppa:
	dput ppa:lordgaav/pmacct "$(CHANGES)"

clean:
	rm -R src || exit 0
	rm config.* || exit 0

pbuild:
	pbuilder-dist "$(DIST)" "$(CHANGES)"

unzip_source: clean
	tar xvf "$(TARBALL)" "$(SRCROOT)"
	mv "$(SRCROOT)/src" .
	rm -R "$(SRCROOT)"
