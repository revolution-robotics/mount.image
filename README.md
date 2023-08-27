# Disk Image Mounter

- [Description](#description)
- [Synopsis](#synopsis)
- [Source Installation](#source-installation)
- [Bugs](#bugs)

## Description

The `mount.image` command mounts the partitions of a (possibly
compressed) disk image on mount points of the form:

```
${MOUNT_IMAGE_BASEDIR}/label
```

where `label` is a partition label. If a mountable partition does not
have a label, then the name of the device associated with the
partition is used instead.

To unmount an image mounted with `mount.image`, use the command
`umount.image` with argument of either the image or one of the
partition mount points.

## Synopsis

```
mount.image DISK-IMAGE [...]
umount.image DISK-IMAGE [...]
```

## Source Installation

To install from source, on the command line run:

```
git clone git@github.com:slewsys/mount.image.git
cd ./mount.image
./autogen.sh
./configure --bindir=${HOME}/bin
make install
```

## Bugs

If you feel that `mount.image` could be improved, please consider
creating an issue at:
[mount.image](https://github.com/revolution-robotics/mount.image/issues).
