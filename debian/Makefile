KEY=CD9C0E84
DIST=trusty
TARBALL=../pmacct_1.5.0~rc3.orig.tar.gz
SRCROOT=pmacct-1.5.0rc3

package:
	dpkg-buildpackage -A -us -uc
 
source: clean
	dpkg-buildpackage -S -k$(KEY)

source_no_sign: clean
	dpkg-buildpackage -S -us -d
 
upload_to_ppa:
	dput ppa:lordgaav/pmacct "$(CHANGES)"

clean:
	rm -R src || exit 0
	rm config.* || exit 0

pbuild:
	pbuilder-dist "$(DIST)" "$(CHANGES)"

get_source_tarball:
	wget -O "$(TARBALL)" "http://www.pmacct.net/$(SRCROOT).tar.gz"

unzip_source: clean
	tar xvf "$(TARBALL)" "$(SRCROOT)"
	mv "$(SRCROOT)/src" .
	rm -R "$(SRCROOT)"
