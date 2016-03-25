ACLOCAL_AMFLAGS = -I config

SUBDIRS = src toolkit
if BUILD_TESTS
SUBDIRS += tests
endif

EXTRA_DIST = Protocol-v3.html UPGRADING packaging libotr.m4 libotr.pc.in \
		bootstrap source_date_epoch

aclocaldir = $(datadir)/aclocal
aclocal_DATA = libotr.m4

pkgconfigdir = $(libdir)/pkgconfig
pkgconfig_DATA = libotr.pc

# Don't include a filename or timestamp in the dist .tar.gz file, so that
# we can create a reproducible tarball (coupled with setting am__tar in
# configure.ac)
override GZIP_ENV='--best --no-name'

source_date_epoch: FORCE
	git log --format=%ct -1 > source_date_epoch
FORCE:
