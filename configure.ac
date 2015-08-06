dnl Process this file with autoconf to produce a configure script.
dnl Created by Anjuta application wizard.

AC_INIT(vaterminal, 0.1)

AC_CONFIG_HEADERS([config.h])

AM_INIT_AUTOMAKE([1.11])

AM_SILENT_RULES([yes])

AC_PROG_CC


AC_ARG_VAR([GLIB_COMPILE_RESOURCES],[the glib-compile-resources programme])
AC_PATH_PROG([GLIB_COMPILE_RESOURCES],[glib-compile-resources],[])
if test -z "$GLIB_COMPILE_RESOURCES"; then
  AC_MSG_ERROR([glib-compile-resources not found])
fi

AC_ARG_VAR([XMLLINT],[the xmllint programme])
AC_PATH_PROG([XMLLINT],[xmllint],[])
if test -z "$XMLLINT"; then
  AC_MSG_ERROR([xmllint not found])
fi



dnl Check for vala
AM_PROG_VALAC([0.10.0])


PKG_CHECK_MODULES(VATERMINAL, [gtk+-3.0 vte-2.91])


AC_OUTPUT([
Makefile
src/Makefile

])
