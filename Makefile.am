## Process this file with automake to produce Makefile.in -*-Makefile-*-

SUBDIRS = bin \
          src \
          doc \
          .

# The ACLOCAL_AMFLAGS are used by 'autoreconf' and by the Makefile rebuild
# rule when they need to run 'aclocal'.
#
ACLOCAL_AMFLAGS = -I autotools


## Ensure that these files make it into the distribution tarball
##
EXTRA_DIST = BUGS HACKING LICENSE

MAINTAINERCLEANFILES = config.status \
                       config.log    \
                       $(PACKAGE)-$(VERSION).tar.gz \
                       *~
