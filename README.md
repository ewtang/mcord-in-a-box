# mcord-in-a-box
Troubleshooting notes for mcord-in-a-box using Kubernetes on Ubuntu 16.04

1. If any openvswitch POD crashes, please stop openvswitch-switch service on host:

<code>$ sudo systemctl stop openvswitch-switch</code>

2. If any libvirt POD crashes, please stop libvirtd service on host:

<code>$ sudo systemctl stop libvirtd.service</code>

<code>$ sudo systemctl disable libvirtd.service</code>

3. If libvirt logs the below permission error:

<code>libvirtd: error while loading shared libraries: libvirt-admin.so.0: cannot stat shared object: Permission denied</code>

Please disable Apparmor for libvirt profile:

<code>$ sudo apparmor_parser -R /etc/apparmor.d/usr.sbin.libvirtd</code>

4. If VTN has not been initialized the host node correctly with state=DEVICE_CREATED:

<code>onos> cordvtn-nodes
Hostname                      Management IP       Data IP             Data Iface     Br-int                  State
ubuntu                        192.168.0.103/24    10.6.1.1/24         fabric         of:00000000abcdef01     DEVICE_CREATED
Total 1 nodes
</code>

Please run cordvtn-node-check:

<code>onos> cordvtn-node-check ubuntu
Current state: DEVICE_CREATED (hint: try init again if the state is not COMPLETE but all settings are OK)

[Integration Bridge Status]
OK br-int=of:00000000abcdef01 available=true {managementAddress=192.168.0.103, protocol=OF_14, channelId=192.168.0.103:56900}
OK vxlan portNum=1 enabled=true {adminState=enabled, portName=vxlan, portMac=ee:e5:3e:60:0d:4e}
NO fabric does not exist

[Interfaces and IP setup]
NO Unable to SSH to ubuntu
</code>

In that case, please check and install openssh-server on host node:

<code>sudo apt-get install openssh-server</code>

<code>onos> cordvtn-node-init ubuntu
onos> cordvtn-nodes
Hostname                      Management IP       Data IP             Data Iface     Br-int                  State
ubuntu                        192.168.0.103/24    10.6.1.1/24         fabric         of:00000000abcdef01     PORT_CREATED
Total 1 nodes
onos> cordvtn-node-check ubuntu
Current state: COMPLETE (hint: try init again if the state is not COMPLETE but all settings are OK)

[Integration Bridge Status]
OK br-int=of:00000000abcdef01 available=true {managementAddress=192.168.0.103, protocol=OF_14, channelId=192.168.0.103:56900}
OK vxlan portNum=1 enabled=true {adminState=enabled, portName=vxlan, portMac=ee:e5:3e:60:0d:4e}
OK fabric portNum=2 enabled=true {adminState=enabled, portName=fabric, portMac=76:9c:fe:c1:4c:aa}

[Interfaces and IP setup]
OK br-int up=true Ips=[172.27.0.1, 10.6.1.1]
OK fabric up=true IpFlushed=true
onos> cordvtn-nodes
Hostname                      Management IP       Data IP             Data Iface     Br-int                  State
ubuntu                        192.168.0.103/24    10.6.1.1/24         fabric         of:00000000abcdef01     COMPLETE
Total 1 nodes
</code>
