.. title:: NCP Bootcamp - Nutanix Networking

.. Adding labels to the beginning of your lab is helpful for linking to the lab from other pages
.. _nutanix_networking_1:

-------------
Nutanix Networking
-------------
 
Session 4

-----------------------------------------------------

Network Configuration
++++++++++++++++++++++++++++++++

.. figure:: images/networkconfiguration.png

Eth2: Network segmentation is designed to separate management traffic from backplane (storage and CVM) traffic 

Separates storage traffic from routable management traffic for security purposes

Separate virtual networks are created for each traffic type


-----------------------------------------------------



VM Network: Enabling IPAM
++++++++++++++++++++++++++++++++

.. figure:: images/EnablingIPAM.png


Enabling IPAM on a User VM Network.

During the VM Network creation process, if you decide to enable IPAM, you will be prompted to provide an IP Pool start and end address

Provide the required values and click Submit



-----------------------------------------------------

Prism Network Dashboard
++++++++++++++++++++++++++++++++

.. figure:: images/PrismNetworkDashboard.png


**Providing Network Connectivity to VMs**


- Two different ways to provide VM connectivity: managed and unmanaged networks
  - With *unmanaged networks*, VMs get direct connection to their VLAN of choice
  - With *managed networks*, AHV (Acropolis master) can perform IP address management (IPAM) for VMs, handing out IP addresses via configurable DHCP pools
  
**While a physical server connects to a physical network, a VM connects to a virtual network.**

- In the case of AHV, it supports unmanaged and managed virtual networks.
  - An unmanaged network is simply a VLAN.
- A managed network is a VLAN plus IPAM.
  - IPAM stands for IP address management.
    - It is the cluster capability to function like a DHCP server to assign an IP address to a VM that sits on the managed network.
   
- You can create a virtual network from the Prism web console, nCLI, or the Nutanix REST API.
- Tech Topx Video walks through AHV networking concepts, including both CLI and Prism examples:  https://youtube/pxQGCXNoD9U

*IPAM*
- CVM administrative L3 process to track device IP addresses
- Creates associations between interface’s MAC address and IP addresses
- Requires predefined pool of IP addresses for IPAM DHCP server





-----------------------------------------------------

Network Visualization
++++++++++++++++++++++++++++++++

.. figure:: images/networkvisualization.png


**Network Visualization in Prism – Specific Host**
*Host NTNX-block_ID-B Details*

- Note: Some newer Intel Gigabit NICs have a hardware limitation that means the maximum MTU they can support is 8996 (instead of 9000).

  - If your interfaces aren't coming up and you are trying to use 9000, this could be the reason and can be difficult to debug.

- Try setting all your MTUs to 8996 and see if it resolves your issues. 




-----------------------------------------------------

vSwitch Implementation (AHV)
++++++++++++++++++++++++++++++++

.. figure:: images/vswitchimplementation.png


**vSwitch Implementation (AHV) Overview**
- While a physical network sits on a physical switch, a virtual network sits on a virtual switch.
  - Two virtual switches are created by default:
   - A Linux bridge (virbr0) and
   - An open vSwitch bridge (br0).
- The Linux bridge is a private virtual switch.
  - It has no physical adapter and is dedicated to the communication between the CVM and the internal interface on the AHV bridge called virbr0.
   - This virbr0 is preconfigured with a private IP address 192.168.5.1.
- The open vSwitch br0 is a public virtual switch.
  - It has one or more physical adapters attached to the network switches.
   - CVMs talk to one another across this open vSwitch.
  - Also, VMs talk to one another and also with the physical network through this open vSwitch.
- Since br0 has similar configuration on all AHV hosts, these br0 collectively appear like a single distributed virtual switch.
  - Also when a virtual network is created from the Prism web console or ACLI, it is created on all AHV hosts.

Each AHV server maintains an OVS instance, and all OVS instances combine to form a single logical switch.





-----------------------------------------------------

Prism Network Dashboard
++++++++++++++++++++++++++++++++

.. figure:: images/NetworkingBestPractices.png






