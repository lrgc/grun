AUTOMAKE_OPTIONS=no-dependencies
SUBDIRS = po intl
localedir=$(datadir)/locale
bin_PROGRAMS = grun
grun_SOURCES = grun.c 
man_MANS = grun.1x
EXTRA_DIST = config.rpath m4/ChangeLog BUGS README INSTALL INSTALL.Win AUTHORS COPYING NEWS TODO grun.1x grun2.xpm consfile gassoc
AM_CFLAGS = -DLOCALEDIR=\""$(localedir)"\" -DDATADIR="$(datadir)" $(GTK_CFLAGS)
AM_LDFLAGS= -Wl,--as-needed -Wl,-z -Wl,defs
grun_LDADD = $(INTLLIBS) $(GTK_LIBS)
grundatadir = $(datadir)/grun
grundata_DATA = gassoc consfile

ACLOCAL_AMFLAGS = -I m4
