# mcord-in-a-box
Troubleshooting notes for mcord-in-a-box using Kubernetes on Ubuntu 16.04

1. If any openvswitch POD crashes, please stop openvswitch-switch service on host:

<code>$ sudo systemctl stop openvswitch-switch</code>

2. If any libvirt POD crashes, please stop libvirtd service on host:

<code>$ sudo systemctl stop libvirtd.service\n$ sudo systemctl disable libvirtd.service</code>

3. If libvirt logs the below permission error:

<code>libvirtd: error while loading shared libraries: libvirt-admin.so.0: cannot stat shared object: Permission denied</code>

please disable Apparmor for libvirt profile:

<code>$ sudo apparmor_parser -R /etc/apparmor.d/usr.sbin.libvirtd</code>
