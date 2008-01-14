AUTOMAKE_OPTIONS=no-dependencies
SUBDIRS = po intl

localedir=$(datadir)/locale

AM_CFLAGS = -DLOCALEDIR=\""$(localedir)"\" -DSYSCONFDIR=\""$(sysconfdir)"\" $(GTK_CFLAGS)
AM_LDFLAGS= -Wl,--as-needed -Wl,-z -Wl,defs

bin_PROGRAMS = grun
grun_SOURCES = grun.c 
grun_LDADD = $(INTLLIBS) $(GTK_LIBS)

dist_man_MANS = grun.1x

dist_sysconf_DATA = gassoc consfile

EXTRA_DIST = config.rpath m4/ChangeLog BUGS README INSTALL AUTHORS COPYING NEWS TODO grun2.xpm

ACLOCAL_AMFLAGS = -I m4
