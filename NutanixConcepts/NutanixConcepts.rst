.. title:: Nutanix NCP Bootcamp

.. toctree::
  :maxdepth: 2
  :caption: Questions
  :name: _labs
  :hidden:

  Q1/Q1
  A1/A1
  Q2/Q2
  A2/A2
  Q3/Q3
  A3/A3
  Q4/Q4
  A4/A4
  Q5/Q5
  A5/A5
  Q6/Q6
  A6/A6
  Q7/Q7
  A7/A7
  Q8/Q8
  A8/A8
  Q9/Q9
  A9/A9
  Q1/Q10
  A10/A10
  
.. _nutanix_concepts:

-------------
Nutanix Concepts
-------------

Session 1

-----------------------------------------------------

What is (Server) Virtualization
++++++++

.. figure:: images/WhatIs.png

- **Host** computer on which hypervisor runs
- **Hypervisor** creates/manages guest VMs and presents VMs with virtual O.S.
- **Guest virtual machine (VM)**  emulation of a physical computer, based on a computer architecture

-----------------------------------------------------

Nutanix HCI 
++++++++++++++++++++++
CPU, Memory, Storage, Network

.. figure:: images/NutanixHCI.png

HCL: Hardware Compatibility Matrix (Support Portal) 
IPMI: Intelligent Platform Management Interface

-----------------------------------------------------

Hardware Platforms
++++++++++++++++++++++

Eligible hardware vendor platforms and configurations as per HCL

.. figure:: images/HardwarePlatforms.png

-----------------------------------------------------

Cluster Construct
++++++++++++++++++++++

A cluster consists of a number of nodes, located in blocks

- **Block** Physical chassis with 1 to 4 nodes
- **Node** Single physical server within block

  - **Node Ports** IPMI, USB, VGA, (Q)SFP
- **Cluster** Logical bundling of physical nodes

.. figure:: images/ClusterConstruct.png

-----------------------------------------------------

Nutanix Hyperconverged
++++++++++++++++++++++

Freedom of choice across hypervisors

.. figure:: images/NutanixHyperconverged.png

-----------------------------------------------------

NTNX Hyper-converged Infrastructure (HCI)
++++++++++++++++++++++

Single pre-configured guest VM (CVM) runs AOS on every node

.. figure:: images/NTNXHyper-convergedInfrastructure.png

-----------------------------------------------------

Nutanix AOS Services
++++++++++++++++++++++

AOS Services run on every CVM in the cluster

.. figure:: images/NutanixAOSServices.png


All hosts within the cluster have visibility into shared Nutanix datastores through the Controller VMs. 
Guest VM data is written locally and replicated on other nodes for high availability.


-----------------------------------------------------

DSF Provides Tiering and Data Locality
++++++++++++++++++++++

Using intelligent data placement algorithms

.. figure:: images/DSFProvidesTieringandDataLocality.png


-----------------------------------------------------

Redundancy Factor (RF)
++++++++++++++++++++++

Either RF2 or RF3

.. figure:: images/RedundancyFactor.png


Why no data is lost upon node failure:
- Write I/O’s directly written to SSD
- Write I/O’s replicated to other nodes (depends on RF)
- Memory only used for Read I/O’s 


-----------------------------------------------------

Intra-cluster CVM-to-CVM Communication
++++++++++++++++++++++

Enables data replication (RF2/RF3), AOS Services monitoring, self-healing

.. figure:: images/Intra-clusterCVM-to-CVMCommunication.png


-----------------------------------------------------

Prism Overview
++++++++++++++++++++++

Prism (Element) vs. Prism Central

.. figure:: images/PrismOverview.png


-----------------------------------------------------

Licensing
++++++++++++++++++++++

License by capacity, appliance, or specific use cases/workloads

.. figure:: images/Licensing.png

AOS (Acropolis)

- Starter
- Pro
- Ultimate

Prism Central

- Standard ("Starter")
- Pro (a.k.a. Prism Pro)


-----------------------------------------------------

Enterprise Cloud Components
++++++++++++++++++++++

License by capacity, appliance, or specific use cases/workloads

.. figure:: images/EnterpriseCloudComponents.png



-----------------------------------------------------

Nutanix Product Portfolio
++++++++++++++++++++++

A journey from Core to Essentials to Enterprise

.. figure:: images/NutanixProductPortfolio.png


-----------------------------------------------------

What’s in a Name?
++++++++++++++++++++++


.. figure:: images/WhatsinaName.png



-----------------------------------------------------

References
++++++++++++++++++++++

Simple Explanation of How Nutanix Works Video
- https://www.youtube.com/watch?v=wfFuohZwi5Q

Nutanix Bible
- https://nutanixbible.com 

my.nutanix.com Support Portal

.. figure:: images/SupportPortal.png


-----------------------------------------------------

