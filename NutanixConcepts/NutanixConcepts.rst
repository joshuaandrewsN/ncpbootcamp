.. Adding labels to the beginning of your lab is helpful for linking to the lab from other pages
.. _example_lab_1:

-------------
Nutanix Concepts
-------------
Session 1

What is (Server) Virtualization
++++++++

.. figure:: images/WhatIs.png

- **Host** computer on which hypervisor runs
- **Hypervisor** creates/manages guest VMs and presents VMs with virtual O.S.
- **Guest virtual machine (VM)**  emulation of a physical computer, based on a computer architecture

Nutanix HCI : CPU, MEMORY, STORAGE, NETWORK
++++++++++++++++++++++

.. figure:: images/NutanixHCI.png

HCL: Hardware Compatibility Matrix (Support Portal) 
IPMI: Intelligent Platform Management Interface

Hardware Platforms
++++++++++++++++++++++

Eligible hardware vendor platforms and configurations as per HCL

.. figure:: images/HardwarePlatforms.png

Cluster Construct
++++++++++++++++++++++

A cluster consists of a number of nodes, located in blocks

- **Block** Physical chassis with 1 to 4 nodes
- **Node** Single physical server within block
  - **Node Ports** IPMI, USB, VGA, (Q)SFP
- **Cluster** Logical bundling of physical nodes

.. figure:: images/ClusterConstruct.png

Nutanix Hyperconverged
++++++++++++++++++++++

Freedom of choice across hypervisors

.. figure:: images/NutanixHyperconverged.png


NTNX Hyper-converged Infrastructure (HCI)
++++++++++++++++++++++

Single pre-configured guest VM (CVM) runs AOS on every node

.. figure:: images/NTNXHyper-convergedInfrastructure.png




Label sections appropriately, see existing labs if further guidance is required. Section titles should begin with present tense verbs to queue what is being done in each section. Use consistent markup for titles, subtitles, sub-subtitles, etc. The markup in the example can serve as a guide but other characters can be used within a given workshop, as long as they are consistent. Other than lab titles (that need to follow a certain linear progression) avoid numbering steps.

Below are examples of standards we should strive to maintain in writing lab guides. *Italics* is used to indicate when information of values external to the lab guide are referenced. **Bold** is used to reference words and phrases in the UI. **Bold** should also be used to highlight the key name in lists containing key/value pairs as shown below. The **>** character is used to show a reasonable progression of clicks, such as traversing a drop down menu. When appropriate, try to consolidate short, simple tasks. ``Literals`` should be used for file paths.

Actions should end with a period, or optionally with a colon as in the case of displaying a list of fields that need to be populated. Keep the language consistent: open, click/select, fill out, log in, and execute.

Use the **figure** directive to include images in your lab guide or appendix. Image files should be included within the Git repository, within an **images** subdirectory within each lab subdirectory.

-----------------------------------------------------

Open \https://<*NUTANIX-CLUSTER-IP*>:9440 in your browser to access Prism. Log in as a user with administrative priveleges.

.. figure:: images/1.png

Click **Network Config > User VM Interfaces > + Create Network**.

.. figure:: images/2.png

Select **Enable IP Address Management** and fill out the following fields:

  - **Name** - VM VLAN
  - **VLAN ID** - *Refer to your Environment Details Worksheet*
  - **Network IP Address/Prefix Length** - *Refer to your Environment Details Worksheet*
  - **Gateway IP Address** - *Refer to your Environment Details Worksheet*
  - **Domain Name Servers** - *Refer to your Environment Details Worksheet*

.. figure:: images/3.png

Click **Submit > Save**.

Takeaways
+++++++++

- Here is where we summarize any key takeaways from the module
- Such as how a Nutanix feature used in the lab delivers value
- Or highlighting a differentiator
