OpenStack Image Maker
=====================

The _openstack-image-maker_ script simplifies the process of creating
and uploading an image to OpenStack.

It invokes the QEMU KVM commands to create the image file, and to run
a virtual machine instance with it, so the operating system can be
installed onto it. It also runs the OpenStack command to upload the
image.

While those steps can be performed directly using the QEMU KVM and
OpenStack commands, this script invokes them with the options needed
for common tasks. Therefore, the user does not have to remember their
complicated options.

## Example

Create the image, prepare it and upload it:

```sh
$ openstack-image-maker create --iso os-install-disc.iso  image.qcow2

$ openstack-image-maker run image.qcow2  # optional

$ openstack-image-maker upload --name "My new image" --min-disk 10  image.qcow2
```

During the preparation step, the operating system is installed onto
the image.  That step is performed over a VNC session, and is similar
to installing the operating system onto any physical or virtual
machine.

## Documentation

A manual page for the utility is in:

- [openstack-image-maker](openstack-image-maker.md)

See the _doc_ directory for details on how to use it:

- [Common setup](doc/common-setup.md)

- [Preparing Linux images](doc/linux-images.md)

- [Preparing Windows images](doc/windows-images.md)

Licence
-------

This utility is distributed in the hope that they will be useful, but
**without any warranty**; without even the implied warranty of
**merchantability** or **fitness for a particular purpose**.  See the
GNU General Public License for more details.

## Reporting issues

Please submit issues using the repository's [GitHub
issues](https://github.com/qcif/openstack-image-maker/issues)

