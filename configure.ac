#                                               -*- Autoconf -*-
# Process this file with autoconf to produce a configure script.

AC_PREREQ([2.69])
AC_INIT([scanasm], [0.1], [evan@eklitzke.org])
AC_CONFIG_AUX_DIR([build-aux])
AC_CONFIG_MACRO_DIR([m4])
AC_CONFIG_SRCDIR([src/main.cc])
AC_CONFIG_HEADERS([src/config.h])

AC_LANG([C++])

# Checks for programs.
AC_PROG_CXX
AC_PROG_CC
AC_PROG_INSTALL

AM_INIT_AUTOMAKE([dist-bzip2 foreign subdir-objects -Wall -Werror])
m4_ifdef([AM_SILENT_RULES], [AM_SILENT_RULES([yes])])

# Checks for libraries.

# Checks for header files.
AC_CHECK_HEADER([elfio/elfio.hpp],,[AC_MSG_ERROR([Failed to find elfio.hpp])])

# Checks for typedefs, structures, and compiler characteristics.
AC_TYPE_SIZE_T
AC_TYPE_UINT8_T

# Checks for library functions.

PKG_CHECK_MODULES([CAPSTONE], [capstone])
AC_SUBST([CAPSTONE_CFLAGS])
AC_SUBST([CAPSTONE_LIBS])
AC_SUBST([CAPSTONE_LDFLAGS])

AC_CONFIG_FILES([Makefile
                 src/Makefile])
AC_OUTPUT
