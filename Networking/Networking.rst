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


