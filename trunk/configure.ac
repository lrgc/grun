dnl ---------------------------------------------------------------------------
dnl Process this file with autoconf to produce a configure script.
dnl $Id$
dnl ---------------------------------------------------------------------------
AC_INIT([Grun], [0.9.3])
AC_CONFIG_SRCDIR([grun.c])
AM_CONFIG_HEADER([config.h])

AM_INIT_AUTOMAKE
AM_MAINTAINER_MODE

AC_ISC_POSIX
AC_USE_SYSTEM_EXTENSIONS

AC_PROG_CC
AM_PROG_CC_STDC
AM_PROG_CC_C_O
AC_HEADER_STDC
AC_PROG_INSTALL
AC_PROG_LN_S
AC_PROG_MAKE_SET

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

dnl ---------------------------------------------------------------------------
dnl check for GTK
dnl ---------------------------------------------------------------------------
AM_PATH_GTK_2_0([2.12.0])

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

AM_GNU_GETTEXT
AM_GNU_GETTEXT_VERSION

dnl ---------------------------------------------------------------------------
dnl Makefiles to create:
dnl ---------------------------------------------------------------------------
AC_CONFIG_FILES([Makefile po/Makefile.in intl/Makefile])
AC_CONFIG_COMMANDS([default],[],[])
AC_OUTPUT
