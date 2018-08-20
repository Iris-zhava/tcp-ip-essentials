## 1.3 Inspect network interfaces

Run

```
ifconfig -a
```

on each host in your topology, and examine the output.

On the romeo and juliet nodes should see two Ethernet interfaces, even though we only set up one link coming out of each one. For example:

```
eth0      Link encap:Ethernet  HWaddr 02:0d:1e:c3:c3:dc  
          inet addr:172.17.1.33  Bcast:172.31.255.255  Mask:255.240.0.0
          inet6 addr: fe80::d:1eff:fec3:c3dc/64 Scope:Link
          UP BROADCAST RUNNING MULTICAST  MTU:1500  Metric:1
          RX packets:17561 errors:0 dropped:0 overruns:0 frame:0
          TX packets:14740 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:1000 
          RX bytes:11047161 (11.0 MB)  TX bytes:1175202 (1.1 MB)

eth1      Link encap:Ethernet  HWaddr 02:d8:ce:5b:bc:45  
          inet addr:10.0.0.2  Bcast:10.0.0.255  Mask:255.255.255.0
          inet6 addr: fe80::d8:ceff:fe5b:bc45/64 Scope:Link
          UP BROADCAST RUNNING MULTICAST  MTU:1500  Metric:1
          RX packets:44 errors:0 dropped:0 overruns:0 frame:0
          TX packets:20 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:1000 
          RX bytes:3476 (3.4 KB)  TX bytes:1858 (1.8 KB)

lo        Link encap:Local Loopback  
          inet addr:127.0.0.1  Mask:255.0.0.0
          inet6 addr: ::1/128 Scope:Host
          UP LOOPBACK RUNNING  MTU:65536  Metric:1
          RX packets:127 errors:0 dropped:0 overruns:0 frame:0
          TX packets:127 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:1 
          RX bytes:7644 (7.6 KB)  TX bytes:7644 (7.6 KB)
```

Every host we reserve on GENI will have a control interface, that we use to SSH into the VM to run commands. Then, it can also have experiment interfaces (one for each link that we connect to the host, when setting it up in the GENI Portal, and with IP address and netmask according to what we configured in the Portal). We will always use the "experiment" interface, not the "control" interface, for our experiments.

### Exercise 8 - Create a network diagram

When you reserve a network topology on GENI, you will control the IP address assigned to each experiment interface. However, the MAC address of the interface will be different each time. On a host with multiple experiment interfaces, the name of the interface (e.g. `eth1`, `eth2`) can also vary. In order to verify your lab results, it is essential that you document the specifics of each network interface in your experiment, and submit it along with your lab report. 

You will document these details in the form of a network diagram, on which you will:

* Draw a connectivity diagram that shows each host and which hosts it is directly connected to.
* Label each host with its hostname.
* Label each network interface (on an experiment network) with the name assigned to it by the OS, e.g. `eth1`, `eth2`.
* Label each network interface (on an experiment network) with its IP address and MAC address.

You will submit at least one network diagram like this for each lab assignments. Some lab assignments may involve more than one network topology, in which case you will submit a network diagram for each topology.