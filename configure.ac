# configure.ac: Autoconf template for bash-dot-files.
#                                               -*- Autoconf -*-
# Process this file with autoconf to produce a configure script.

AC_PREREQ([2.71])
AC_INIT([mount.image], [1.0.0], [])
AM_INIT_AUTOMAKE([foreign])

if test -f ~/bin/unset-toplevel-variables; then
    source ~/bin/unset-toplevel-variables
fi

AS_IF(
  [test ."$bindir" = .'${exec_prefix}/bin'],
    [bindir=$HOME])

LOCAL_PREFIX=/usr/local/sbin${PATH_SEPARATOR}/usr/local/bin${PATH_SEPARATOR}

AC_MSG_CHECKING([whether to search optional path])
AC_ARG_WITH([opt-path],
  [AS_HELP_STRING([--with-opt-path@<:@=PATH@:>@],
    [search optional PATH @{:@default: /opt/local/bin@:}@])],
  [], [with_opt_path=check])
if test ."$with_opt_path" = .'yes' || test ."$with_opt_path" = .'check'; then
    if test -d /opt/local/bin; then
        OPT_PREFIX=/opt/local/sbin${PATH_SEPARATOR}/opt/local/bin
    fi
elif test ! ."$with_opt_path" = .'no'; then
    if test -d "$with_opt_path"; then
        OPT_PREFIX=${with_opt_path}
    else
        AC_MSG_WARN([${with_opt_path}: No such file or directory])
    fi
fi
AC_MSG_RESULT([${OPT_PREFIX:-no}])
OPT_PATHS=$(echo "$OPT_PREFIX" | tr "${PATH_SEPARATOR}" ' ')
AC_SUBST([OPT_PATHS], ["$OPT_PATHS"])
OPT_PREFIX=${OPT_PREFIX:+"${OPT_PREFIX}${PATH_SEPARATOR}"}

# Checks for programs.
AC_PATH_PROG([BASH_CMD],        [bash],               [], [${OPT_PREFIX}${PATH}])
AC_PATH_PROG([BZIP2_CMD],       [bzip2],              [], [${OPT_PREFIX}${PATH}])

AC_PATH_PROGS([CAT_CMD],        [gcat cat],           [], [${OPT_PREFIX}${PATH}])

AC_PATH_PROG([DMSETUP_CMD],     [dmsetup],            [], [${OPT_PREFIX}${PATH}])
AC_PATH_PROG([ED_CMD],          [ed],                 [], [${LOCAL_PREFIX}${PATH}])
AC_PATH_PROG([FINDMNT_CMD],     [findmnt])
AC_PATH_PROG([FLOCK_CMD],       [flock],              [], [${OPT_PREFIX}${PATH}])
AC_PATH_PROG([GETOPT_CMD],      [getopt],             [], [${OPT_PREFIX}${PATH}])

AC_PATH_PROGS([GREP_CMD],       [ggrep grep],         [], [${OPT_PREFIX}${PATH}])

AC_PATH_PROG([GZIP_CMD],        [gzip],               [], [${OPT_PREFIX}${PATH}])

AC_PATH_PROGS([INSTALL_CMD],    [ginstall install],   [], [${OPT_PREFIX}${PATH}])

AC_PATH_PROG([JQ_CMD],          [jq])
AC_PATH_PROG([KPARTX_CMD],      [kpartx])
AC_PATH_PROG([LOSETUP_CMD],     [losetup])
AC_PATH_PROG([LSBLK_CMD],       [lsblk])
AC_PATH_PROG([LVS_CMD],         [lvs])
AC_PATH_PROG([LZIP_CMD],        [lzip],               [], [${OPT_PREFIX}${PATH}])
AC_PATH_PROG([LZMA_CMD],        [lzma],               [], [${OPT_PREFIX}${PATH}])
AC_PATH_PROG([LZOP_CMD],        [lzop],               [], [${OPT_PREFIX}${PATH}])

AC_PATH_PROGS([MKTEMP_CMD],     [gmktemp mktemp],     [], [${OPT_PREFIX}${PATH}])

AC_PATH_PROG([MOUNT_CMD],       [mount])

AC_PATH_PROGS([MV_CMD],         [gmv mv],             [], [${OPT_PREFIX}${PATH}])

AC_PATH_PROG([PARTPROBE_CMD],   [partprobe])

AC_PATH_PROGS([READLINK_CMD],   [greadlink readlink], [], [${OPT_PREFIX}${PATH}])
AC_PATH_PROGS([RM_CMD],         [grm rm],             [], [${OPT_PREFIX}${PATH}])
AC_PATH_PROGS([RMDIR_CMD],      [grmdir rmdir],       [], [${OPT_PREFIX}${PATH}])
AC_PATH_PROGS([SED_CMD],        [gsed sed],           [], [${OPT_PREFIX}${PATH}])
AC_PATH_PROGS([SEQ_CMD],        [gseq seq],           [], [${OPT_PREFIX}${PATH}])
AC_PATH_PROGS([SLEEP_CMD],      [gsleep sleep],       [], [${OPT_PREFIX}${PATH}])

AC_PATH_PROG([SUDO_CMD],        [sudo],               [], [${OPT_PREFIX}${PATH}])

AC_PATH_PROGS([TR_CMD],         [gtr tr],             [], [${OPT_PREFIX}${PATH}])

AC_PATH_PROG([UMOUNT_CMD],      [umount])
AC_PATH_PROG([UNZIP_CMD],       [unzip],              [], [${OPT_PREFIX}${PATH}])
AC_PATH_PROG([VGCHANGE_CMD],    [vgchange])
AC_PATH_PROG([VGS_CMD],         [vgs])
AC_PATH_PROG([XZ_CMD],          [xz],                 [], [${OPT_PREFIX}${PATH}])
AC_PATH_PROG([ZSTD_CMD],        [zstd],               [], [${OPT_PREFIX}${PATH}])

AC_CONFIG_FILES([Makefile])
AC_CONFIG_FILES([mount.image],                          [chmod +x mount.image;
                                                         ln -sf mount.image umount.image])
AC_OUTPUT
