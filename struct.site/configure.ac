#                                               -*- Autoconf -*-
# Process this file with autoconf to produce a configure script.

AC_PREREQ(2.61)
AC_INIT([libnss-exo], [1.0])
AM_INIT_AUTOMAKE
AM_INIT_AUTOMAKE([subdir-objects])
AC_CONFIG_MACRO_DIRS([m4])
AC_CONFIG_SRCDIR([../src/tool.h])
AC_CONFIG_HEADER([config.h])
AC_PREFIX_DEFAULT([])

#AC_ARG_WITH(passwd-db,
#    AC_HELP_STRING([--with-passwd-db],
#            [Specify users' db location, defaults to /var/db/passwd.sqlite]),
#    AC_DEFINE_UNQUOTED([NSS_SQLITE_PASSWD_DB], ["$withval"], [Users' database]),
#    AC_DEFINE([NSS_SQLITE_PASSWD_DB], ["/var/db/passwd.sqlite"], [Users' database]))
#
#AC_ARG_WITH(shadow-db,
#    AC_HELP_STRING([--with-shadow-db],
#            [Specify shadow db location (containing users' passwords), defaults 
#    to /var/db/shadow.sqlite]),
#    AC_DEFINE_UNQUOTED([NSS_SQLITE_SHADOW_DB], ["$withval"], [Shadow database]),
#    AC_DEFINE([NSS_SQLITE_SHADOW_DB], ["/var/db/shadow.sqlite"], [Shadow database]))


#CFLAGS="$CLAGS $(xml2-config --cflags) $(xml2-config --libs)"
CFLAGS="$CLAGS -lczmq -lzmq"

AC_ARG_ENABLE(debug, 
    AC_HELP_STRING([--enable-debug],
            [Enable debug statements using syslog]),
    AC_DEFINE([DEBUG], [], [Enable debugging])
    CFLAGS="$CFLAGS -g")



# Checks for programs.
AC_PROG_CC
AC_PROG_LIBTOOL

# Checks for libraries.
#AC_CHECK_LIB([sqlite3], [sqlite3_open])

# Checks for header files.
AC_HEADER_STDC
#AC_CHECK_HEADERS([libxml/parser.h libxml/tree.h libxml/xpath.h libxml/xpathInternals.h errno.h grp.h malloc.h nss.h pthread.h pwd.h shadow.h string.h syslog.h unistd.h],
AC_CHECK_HEADERS([errno.h grp.h malloc.h nss.h pthread.h pwd.h shadow.h string.h syslog.h unistd.h],
    [], AC_MSG_ERROR([Missing headers]))

# Checks for typedefs, structures, and compiler characteristics.
AC_C_CONST
AC_TYPE_UID_T
AC_TYPE_SIZE_T

# Checks for library functions.
AC_FUNC_MALLOC
AC_FUNC_REALLOC
AC_CHECK_FUNCS([strdup])


AC_CONFIG_FILES([Makefile])
AC_OUTPUT