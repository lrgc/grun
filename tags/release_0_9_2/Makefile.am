AUTOMAKE_OPTIONS=no-dependencies
SUBDIRS = po intl
localedir=$(datadir)/locale
bin_PROGRAMS = grun
grun_SOURCES = grun.c 
man_MANS = grun.1x
EXTRA_DIST = Makefile.vc6 BUGS README INSTALL INSTALL.Win AUTHORS COPYING NEWS TODO LANGUAGES grun.1x grun2.xpm consfile gassoc messages.po
CPPFLAGS = -DLOCALEDIR=\""$(localedir)"\"
LDADD = $(INTLLIBS)
grundatadir = $(datadir)/grun
grundata_DATA = gassoc consfile
