dnl Process this file with autoconf to produce a configure script. -*-Autoconf-*-

dnl +-------------------------+
dnl |  Autotools Boilerplate  |
dnl +-------------------------+

dnl Ensure that a recent-enough version of Autoconf is being used
AC_PREREQ([2.69])

dnl Defines the following m4 macros, output variables, and preprocessor
dnl symbols. Only the m4 macros have the 'AC_' prefix:
dnl
dnl     [AC_] PACKAGE_NAME
dnl     [AC_]PACKAGE_TARNAME
dnl     [AC_]PACKAGE_VERSION
dnl     [AC_]PACKAGE_STRING     ("<PACKAGE> <VERSION>")
dnl     [AC_]PACKAGE_BUGREPORT
dnl     [AC_]PACKAGE_URL
dnl
AC_INIT([[ADS Clock]],
        [[0.1.0-snapshot]],
        [[Alan D. Salewski <salewski@att.net>]],
        [[ads-clock]],
        [[https://github.com/salewski/ads-clock]])

AC_CONFIG_AUX_DIR([build-aux])

dnl Indicate dir where our custom m4 macros may be found (future
dnl proofing; as of may not be used yet...)
AC_CONFIG_MACRO_DIR([autotools])

dnl Turn on all Automake warnings and report them as errors
AM_INIT_AUTOMAKE([-Wall -Werror foreign])


dnl AC_SUBST([DFLT_MAINTAINER_NAME])
dnl AC_SUBST([DFLT_MAINTAINER_EMAIL])
dnl AC_SUBST([DFLT_MAINTAINER_FULL])


dnl +------------------------+
dnl |  Checks for programs.  |
dnl +------------------------+

dnl makes $(LN_S) available in our Makefile.am files
AC_PROG_LN_S


# We've only tested with bash 4.x, but are we really likely to encounter
# versions older than that on a developer's workstation these days? If we need
# to be more specific, please let the author know!
AC_PATH_PROG(BASH_SH, bash)
if test -z "$BASH_SH"; then
    AC_MSG_ERROR([bash not found])
fi

AC_PATH_PROG([CAT], [cat])
if test -z "$CAT"; then
    AC_MSG_ERROR([cat not found])
fi

AC_PATH_PROG([CHGRP], [chgrp])
if test -z "$CHGRP"; then
    AC_MSG_ERROR([chgrp not found])
fi

AC_PATH_PROG([CHOWN], [chown])
if test -z "$CHOWN"; then
    AC_MSG_ERROR([chown not found])
fi

AC_PATH_PROG([EXPR_PROG], [expr])
if test -z "EXPR_PROG"; then
    AC_MSG_ERROR([expr not found])
fi

AC_PATH_PROG([FIND], [find])
if test -z "$FIND"; then
    AC_MSG_ERROR([find not found]);dnl Ha!
fi

AC_PATH_PROG([GREP], [grep])
if test -z "$GREP"; then
    AC_MSG_ERROR([grep not found])
fi

AC_PATH_PROG([HEAD_PROG], [head])
if test -z "$HEAD_PROG"; then
    AC_MSG_ERROR([head not found])
fi

AC_PATH_PROG([ID_PROG], [id])
if test -z "$ID_PROG"; then
    AC_MSG_ERROR([id program not found])
fi

AC_PATH_PROG([SED], [sed])
if test -z "$SED"; then
    AC_MSG_ERROR([sed not found])
fi

AC_PATH_PROG([RM], [rm])
if test -z "$RM"; then
    AC_MSG_ERROR([rm not found])
fi

AC_PATH_PROG([RMDIR], [rmdir])
if test -z "$RMDIR"; then
    AC_MSG_ERROR([rmdir not found])
fi

dnl # There are several implementations of the 'seq' program; most GNU/Linux
dnl # distributions use the version provided by the GNU 'coreutils' project.
dnl #
dnl # See:
dnl #     https://en.wikipedia.org/wiki/Seq_(Unix)
dnl #     http://www.gnu.org/software/coreutils/coreutils.html
dnl #     http://tools.suckless.org/9base
dnl #
dnl # One Debian systems, unless you have an exotic setup, you probably have the
dnl # 'coreutils' package installed already.
dnl # 
dnl AC_PATH_PROG([SEQ_PROG], [seq])
dnl if test -z "$SEQ_PROG"; then
dnl     AC_MSG_ERROR([seq not found])
dnl fi


# The 'toilet' program (from the TOIlet project) is the heart of the ads-clock
# display. The description from the upstream web site:
# <quote>
#     The TOIlet project attempts to create a free replacement for the ​FIGlet
#     utility. TOIlet stands for “The Other Implementation’s letters”, coined
#     after FIGlet’s “Frank, Ian and Glen’s letters”.
# </quote>
# 
# See:
#     http://caca.zoy.org/wiki/toilet
#
AC_PATH_PROG([TOILET_PROG], [toilet])
if test -z "$TOILET_PROG"; then
    AC_MSG_ERROR([toilet not found])dnl Ha!

fi


# The 'tput' program comes from 'ncurses'.
#
# See:
#     http://invisible-island.net/ncurses/
#
# On Debian systems the 'tput' program is provided by the 'nurses-bin' package
# (source package name: 'ncurses')
#
AC_PATH_PROG([TPUT_PROG], [tput])
if test -z "$TPUT_PROG"; then
    AC_MSG_ERROR([tput not found])
fi

AC_PATH_PROG([TR_PROG], [tr])
if test -z "$TR_PROG"; then
    AC_MSG_ERROR([tr not found])
fi

dnl AC_PATH_PROG([GROUPADD], [groupadd])
dnl if test -z "$GROUPADD"; then
dnl     AC_MSG_ERROR([groupadd program not found])
dnl fi
dnl AC_PATH_PROG([USERADD], [useradd])
dnl if test -z "$USERADD"; then
dnl     AC_MSG_ERROR([useradd program not found])
dnl fi
dnl AC_PATH_PROG([USERMOD], [usermod])
dnl if test -z "$USERMOD"; then
dnl     AC_MSG_ERROR([usermod program not found])
dnl fi


# pod2man comes with Perl. We check for it directly, though, because GNU/Linux
# distribution packaging sometimes makes it available as a standalone package.
# We use pod2man at build time to create some of our man pages.
AC_PATH_PROG([POD2MAN], [pod2man])
if test -z "$POD2MAN"; then
    AC_MSG_ERROR([pod2man program not found])
fi

# On Debian systems, the watch(1) program is provided by the 'procps' package.
#
# See:
#     https://gitlab.com/procps-ng/procps
#
AC_PATH_PROG([WATCH_PROG], [watch])
if test -z "$WATCH_PROG"; then
    AC_MSG_ERROR([watch not found])
fi



dnl +------------------------+
dnl |  Checks for Libraries  |
dnl +------------------------+
dnl None!

dnl +----------------------+
dnl |  Checks for Headers  |
dnl +----------------------+
dnl None!

dnl +------------------------------------------------------------------+
dnl |  Checks for typedefs, structures, and compiler characteristics.  |
dnl +------------------------------------------------------------------+
dnl None!

dnl +---------------------------------+
dnl |  Checks for library functions.  |
dnl +---------------------------------+
dnl None!


## The 'do_subst' Makefile var is the conventional name for manual
## filtering process that needs to be done at build time.
##
## Basically, any file we generate that is not a Makefile should be
## filtered at build time rather than at configure time; at build
## time, autotools variables will be fully expanded (well, expanded
## recursively, which amounts to the same thing) and allows any of the
## make vars to be overridden on the 'make' command line. This also
## avoids other kludgey hacks, such as eval'ing shell variables to
## expand them at configure time).
##
## Note that we replace all of the autoconf installation directory
## vars (see "Installation Directory Variables" in the autoconf
## manual) and most of the autoconf preset output variables (see
## "Preset Output Variables" in the autoconf manual). The exceptions
## to that latter are flag vars to the C/C++/Fortran compilers,
## linkers, etc. (CFLAGS and friends), and the 'configure_input' var,
## which we have to provide our own variation of. We also omit
## 'builddir' (which is always '.'); in this last case, what you
## probably want instead is 'abs_builddir', which we provide.
[
do_subst_command='do_subst = sed \
  -e '"'"'s,[@]PACKAGE[@],$(PACKAGE),g'"'"' \
  -e '"'"'s,[@]PACKAGE_NAME[@],$(PACKAGE_NAME),g'"'"' \
  -e '"'"'s,[@]PACKAGE_TARNAME[@],$(PACKAGE_TARNAME),g'"'"' \
  -e '"'"'s,[@]PACKAGE_VERSION[@],$(PACKAGE_VERSION),g'"'"' \
  -e '"'"'s,[@]PACKAGE_STRING[@],$(PACKAGE_STRING),g'"'"' \
  -e '"'"'s,[@]PACKAGE_BUGREPORT[@],$(PACKAGE_BUGREPORT),g'"'"' \
  -e '"'"'s,[@]PACKAGE_URL[@],$(PACKAGE_URL),g'"'"' \
  \
  -e '"'"'s,[@]VERSION[@],$(VERSION),g'"'"' \
  -e '"'"'s,[@]PATH_SEPARATOR[@],$(PATH_SEPARATOR),g'"'"' \
  -e '"'"'s,[@]configure_input[@],Generated from $@.in; do not edit by hand.,g'"'"' \
  -e "s,[@]BUILD_DATE[@],$$(date '"'"'+%Y-%m-%d %H:%M:%S'"'"'),g" \
  \
  -e '"'"'s,[@]bindir[@],$(bindir),g'"'"' \
  -e '"'"'s,[@]datadir[@],$(datadir),g'"'"' \
  -e '"'"'s,[@]exec_prefix[@],$(exec_prefix),g'"'"' \
  -e '"'"'s,[@]includedir[@],$(includedir),g'"'"' \
  -e '"'"'s,[@]infodir[@],$(infodir),g'"'"' \
  -e '"'"'s,[@]libdir[@],$(libdir),g'"'"' \
  -e '"'"'s,[@]libexecdir[@],$(libexecdir),g'"'"' \
  -e '"'"'s,[@]localstatedir[@],$(localstatedir),g'"'"' \
  -e '"'"'s,[@]mandir[@],$(mandir),g'"'"' \
  -e '"'"'s,[@]oldincludedir[@],$(oldincludedir),g'"'"' \
  -e '"'"'s,[@]prefix[@],$(prefix),g'"'"' \
  -e '"'"'s,[@]sbindir[@],$(sbindir),g'"'"' \
  -e '"'"'s,[@]sharedstatedir[@],$(sharedstatedir),g'"'"' \
  -e '"'"'s,[@]sysconfdir[@],$(sysconfdir),g'"'"' \
  \
  -e '"'"'s,[@]abs_builddir[@],$(abs_builddir),g'"'"' \
  -e '"'"'s,[@]abs_srcdir[@],$(abs_srcdir),g'"'"' \
  -e '"'"'s,[@]abs_top_builddir[@],$(abs_top_builddir),g'"'"' \
  -e '"'"'s,[@]srcdir[@],$(srcdir),g'"'"' \
  -e '"'"'s,[@]top_builddir[@],$(top_builddir),g'"'"' \
  -e '"'"'s,[@]top_srcdir[@],$(top_srcdir),g'"'"' \
  \
  -e '"'"'s,[@]POD2MAN[@],$(POD2MAN),g'"'"' \
  \
  -e '"'"'s,[@]BASH_SH[@],$(BASH_SH),g'"'"' \
  -e '"'"'s,[@]CAT[@],$(CAT),g'"'"' \
  -e '"'"'s,[@]CHGRP[@],$(CHGRP),g'"'"' \
  -e '"'"'s,[@]CHOWN[@],$(CHOWN),g'"'"' \
  -e '"'"'s,[@]EXPR_PROG[@],$(EXPR_PROG),g'"'"' \
  -e '"'"'s,[@]FIND[@],$(FIND),g'"'"' \
  -e '"'"'s,[@]GREP[@],$(GREP),g'"'"' \
  -e '"'"'s,[@]HEAD_PROG[@],$(HEAD_PROG),g'"'"' \
  -e '"'"'s,[@]ID_PROG[@],$(ID_PROG),g'"'"' \
  -e '"'"'s,[@]RM[@],$(RM),g'"'"' \
  -e '"'"'s,[@]RMDIR[@],$(RMDIR),g'"'"' \
  -e '"'"'s,[@]SED[@],$(SED),g'"'"' \
  -e '"'"'s,[@]TOILET_PROG[@],$(TOILET_PROG),g'"'"' \
  -e '"'"'s,[@]TPUT_PROG[@],$(TPUT_PROG),g'"'"' \
  -e '"'"'s,[@]TR_PROG[@],$(TR_PROG),g'"'"' \
  -e '"'"'s,[@]WATCH_PROG[@],$(WATCH_PROG),g'"'"' \
'
]
AC_SUBST([do_subst_command])

# It's common for makefile scripts to need to "sed sanitize" the value of a
# variable in order to use it on the left side of a sed 's' (substitution)
# command. To obtain a "sed sanitized" copy of any variable, echo its value to:
#     $(sed_slsanitize)
#
# Example:
#     vers_sedslsanitized=$$(printf "%s\n" "-$(VERSION)" | $(sed_slsanitize)) ;\
#     nonvers=$$(echo progwithvers | sed -e "s/$${vers_sedslsanitized}$$//")
[
sed_slsanitize_command='sed_slsanitize = sed \
  -e '"'"'s!\([]^\*\$\/&[]\)!\\\1!g'"'"' \
  -e '"'"'s![-]![-]!g'"'"' \
'
]
AC_SUBST([sed_slsanitize_command])

# Similar to 'sed_slsanitize' above, but for the replacement text on the right
# side of a sed 's' (substitution) command. On the right side of a sed 's'
# substitution we only need to escape backslashes and amperdoodle chars.
[
sed_srsanitize_command='sed_srsanitize = sed \
  -e '"'"'s!\([\/&]\)!\\\1!g'"'"' \
'
]
AC_SUBST([sed_srsanitize_command])


dnl AC_CONFIG_FILES requires a list of file paths, but we do not want
dnl to have to maintain the list by hand.
dnl
dnl To obtain a list of of paths to all Makefiles we want to have
dnl generated, based on the existence of Makefile.am files, run the
dnl following shell snippet (for use as the argument to
dnl AC_CONFIG_FILES).
dnl
dnl Note that we take care to m4-quote the output strings. Filenames
dnl with square brackets in them will break this, so don't do that.
dnl
dnl   find . -type f -name 'Makefile.am' -printf "%P\n"| sed -e 's/\.am$//g;s/^/[/g;s/$/]/g' | sort
dnl
dnl Cookbook for emacs users:
dnl   1. Delete all [**/Makefile] entries from args to AC_CONFIG_FILES
dnl
dnl   2. Copy the above 'find' command line (M-w)
dnl
dnl   3. Place point (cursor) on a line by itself after
dnl      AC_CONFIG_FILES's opening paren and set mark (C-SPACE)
dnl
dnl   4. Run the 'find' command, inserting the output at point:
dnl          C-u M-! C-y RET
dnl
dnl   5. Use `indent-region' (C-M-\) to indent the quoted
dnl      strings. Region is already set up because we set the mark above.

dnl Declare our output Makefiles
AC_CONFIG_FILES(
    [Makefile]
    [bin/Makefile]
    [doc/Makefile]
    [doc/images/Makefile]
    [doc/video/Makefile]
    [src/Makefile]
    [src/main/Makefile]
    [src/main/bash/Makefile]
    [src/main/bash/bin/Makefile]
)

dnl Actually output the declared files
AC_OUTPUT


# I know that shell functions are not considered portable to old ancient
# *nices, but users of such systems are unlikely users of the ads-clock
# (please let me know if this assumption is incorrect!). In most cases, it may
# be that we may need to beef something up to /find/ it, but there should
# definately be a shell installed that understands functions...
#
# Prints on stdout the fully expanded path represented by the value in
# the SHELL_VAR_NAME param. Does /not/ assign the expanded value to
# the named shell var.
#
# __poor_mans_expand_file_name( SHELL_VAR_NAME )
#
# @param SHELL_VAR_NAME should be set to the /name/ of an existing
#                       shell variable whose value contains a
#                       directory path that may or may not need
#                       expansion of the configure shell variables
#                       ($prefix, and the like).
#
__poor_mans_expand_file_name () {
    _tmp_name=$1
    _tmp_last="`eval echo '${'"${_tmp_name}"'}'`"
    if test -z "${_tmp_last}"; then
        printf "__poor_mans_expand_file_name() (WARNING): var \"%s\" is empty\n" \
          "${_tmp_name}" 1>&2
        return 0;  # nothing to do
    fi
    _tmp_last_expanded="`eval echo ${_tmp_last}`"
    while test "${_tmp_last_expanded}" != "${_tmp_last}"; do

        # Set 'last' hold var to most recently expanded version...
        _tmp_last="${_tmp_last_expanded}"

        # ...and try to expand further.
        _tmp_last_expanded="`eval echo ${_tmp_last_expanded}`"
    done
    printf "%s\n" "${_tmp_last_expanded}"
    unset _tmp_last_expanded
    unset _tmp_last
    unset _tmp_name
    return 0;
}

dnl show user a summary of the configured options
printf "\n"
printf "${PACKAGE} has been configured with the following options:\n"
printf "                        Prefix: %s\n" "`__poor_mans_expand_file_name prefix`"
printf "                 User binaries: %s\n" "`__poor_mans_expand_file_name bindir`"
printf "               System binaries: %s\n" "`__poor_mans_expand_file_name sbindir`"
printf "           Configuration files: %s\n" "`__poor_mans_expand_file_name sysconfdir`"
printf "                  Manual pages: %s\n" "`__poor_mans_expand_file_name mandir`"
printf "\n"
printf "                          bash: %s\n" "`__poor_mans_expand_file_name BASH_SH`"
printf "\n"


## DEBUG: Show all variables set in the shell at the end of 'configure' run
## set | grep -v '^[ {}]' | sort
