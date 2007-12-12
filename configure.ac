dnl ---------------------------------------------------------------------------
dnl Process this file with autoconf to produce a configure script.
dnl $Id$
dnl ---------------------------------------------------------------------------
AC_INIT
AC_CONFIG_SRCDIR([grun.c])
GRUN_VERSION=0.9.2

dnl ---------------------------------------------------------------------------
dnl for automake:
dnl ---------------------------------------------------------------------------
AUTOMAKE_OPTIONS=no-dependencies
VERSION=$GRUN_VERSION
PACKAGE=grun


dnl ---------------------------------------------------------------------------
dnl Initialize automake now
dnl ---------------------------------------------------------------------------
AM_INIT_AUTOMAKE($PACKAGE, $VERSION)
AC_SUBST(GRUN_VERSION)
AC_SUBST(VERSION)
AC_SUBST(PACKAGE)

dnl ---------------------------------------------------------------------------
dnl checks for needed compilers
dnl ---------------------------------------------------------------------------
dnl CFLAGS=""
dnl if test x${CFLAGS+set} = xset ; then
dnl   :
dnl else
dnl   CFLAGS="-O2 -g"
dnl fi

AC_PROG_CC
AC_GNU_SOURCE

dnl ---------------------------------------------------------------------------
dnl clean compiles
dnl ---------------------------------------------------------------------------
compiler_warnings=yes
AC_ARG_ENABLE(
	warnings,
	[  --disable-warnings      turn OFF gcc compiler warnings (not recommended)],
	[if test $enableval = no; then
		compiler_warnings=no
	fi]
	)

dnl ---------------------------------------------------------------------------
dnl now some other stuff
dnl AC_CANONICAL_HOST  ... needs config.guess
dnl ---------------------------------------------------------------------------
AC_CONFIG_HEADERS([config.h])
AM_SANITY_CHECK

dnl ---------------------------------------------------------------------------
dnl Internationalization
dnl ---------------------------------------------------------------------------
ALL_LINGUAS="de es fr pt"
AM_GNU_GETTEXT

dnl ---------------------------------------------------------------------------
dnl check for GTK
dnl ---------------------------------------------------------------------------
AM_PATH_GTK_2_0(2.12.0)

dnl ---------------------------------------------------------------------------
dnl enable GUI/console type checking
dnl ---------------------------------------------------------------------------
use_testfile=no
AC_ARG_ENABLE(
	testfile,
	[  --enable-testfile       enable testfile code yes/no (default=no) ],
	[if test $enableval = yes; then
		AC_DEFINE(TESTFILE, [], "Enable testfile code")
		use_testfile=yes
	fi]
	)
def_xterm=xterm
AC_ARG_WITH(
	default_xterm,
	[  --with-default-xterm=X  set default xterm (only for testfile) default=xterm ],
	[if test x$with_default_xterm != x; then
		def_xterm=$with_default_xterm
	fi]
	)
if test $use_testfile = yes; then
	AC_DEFINE_UNQUOTED(XTERM, "$def_xterm", "Default xterm binary")
fi

dnl ---------------------------------------------------------------------------
dnl enable file extension associations
dnl ---------------------------------------------------------------------------
AC_ARG_ENABLE(
	associations,
	[  --enable-associations   enable associations code yes/no (default=no) ],
	[if test $enableval = yes; then
		AC_DEFINE(ASSOC, [], "Enable associations code")
	fi]
	)

dnl ---------------------------------------------------------------------------
dnl checks for correctly defined types
dnl ---------------------------------------------------------------------------
AC_TYPE_SIZE_T

dnl ---------------------------------------------------------------------------
dnl checks for header files & functions
dnl ---------------------------------------------------------------------------
AC_CHECK_HEADERS(string.h unistd.h)

dnl ---------------------------------------------------------------------------
dnl Makefiles to create:
dnl ---------------------------------------------------------------------------
AC_CONFIG_FILES([Makefile intl/Makefile po/Makefile.in])
AC_CONFIG_COMMANDS([default],[],[])
AC_OUTPUT
