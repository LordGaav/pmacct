KEY=CD9C0E84
DIST=trusty

package:
	dpkg-buildpackage -A -us -uc
 
source:
	dpkg-buildpackage -S -k$(KEY)
 
upload_to_ppa:
	dput ppa:lordgaav/pmacct "$(CHANGES)"

clean:
	rm -R src
	rm config.*

pbuild:
	pbuilder-dist "$(DIST)" "$(CHANGES)"
