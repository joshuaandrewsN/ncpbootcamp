.. Adding labels to the beginning of your lab is helpful for linking to the lab from other pages
.. _Managing_a_Nutanix_Cluster_1:

-------------
Managing a Nutanix Cluster
-------------

Session 2

-----------------------------------------------------

Cluster Management
++++++++

Graphical interface (UI) and Command Line (CLI)

.. figure:: images/ClusterManagement.png


**Prism (HTML5 GUI)**

- Prism (Element)

- Prism Central (Pro)

**Nutanix PowerShell**

**REST API Explorer**

**CLI** (SSH, e.g. PuTTY)

- Bash (Linux shell)

- nCLI  (Nutanix CLI)

- aCLI (Acropolis CLI)

- eCLI (Support)


There are several methods to manage a Nutanix implementation
""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""


- Graphical UI – Prism Element and Prism Central

  - Preferred method for management
  - Manage entire environment (when using Prism Central)

- Command Line Interfaces

  - nCLI – Get status and configure entities within a cluster
  - ACLI – Manage the Acropolis portion of the Nutanix environment

- Nutanix PowerShell Cmdlets – For use with Windows PowerShell

- REST API – Exposes all GUI components for orchestration and automation


-----------------------------------------------------


Prism Architecture
++++++++++++++++++

Prism Element, Prism Central

.. figure:: images/PrismArchitecture.png

Prism is the Nutanix UI used for administrative purposes and is broken down into two main components:

- Prism Central (PC)
  - 1:many cluster manager that provides a single, centralized management interface for managing multiple Nutanix clusters.  
  - Optional software appliance (VM).
- Prism Element (PE)
  - Localized cluster manager built-in to the CVM and used for local cluster management and operations.  
  - 1:1 cluster manager

Prism listens on ports 80 and 9440. If HTTP traffic comes in on port 80 it is redirected to HTTPS on port 9440.

Interfaces
""""""""""

 - HTML5 (PE/PC)
 - API (e.g. REST, Powershell, Java, Python)
 - CLI (aCLI, nCLI)

Configuration management:
"""""""""""""""""""""""""

- VM management:
  - VM Operations: Create, delete, update, power, pause/resume VMs, access via remote console
  - Resource Scheduling: Determine initial placement of VMs based on CPU and memory availability
  - Migration: Live migrate VMs across nodes
  - Snapshots and Clones: Rapidly create efficient snapshots and clones of VMs
  - High Availability: Auto-restart VMs on a different host upon host failures.
  - IP Management: Assign dynamic IP addresses to a VM at creation for the life of the VM. Acropolis uses VXLAN tunnels for IP address management.
  - Analytics: Monitor and report key metrics for both VMs and the infrastructure, including hypervisor and physical nodes
  - Remote Console: Remote access all types of virtual machines and operating systems to operate at the console level.

- Host Management:
  - Host Profiles: Standardize configuration of hosts within a cluster based on user-provided information
  - Virtual Networking: Setup and configure VLAN-backed virtual networks spanning the cluster. Use built-in IP management
  - Upgrades: Non-Disruptive rolling Hypervisor upgrade in a Nutanix cluster
  - Maintenance Mode: Put hosts into maintenance mode for upgrades and host removals
  - Scaling: Easily add and remove nodes in minutes

- Storage policy - compression, deduplication, erasure coding
- Data protection – snapshots, backup, disaster recovery, replication
- Monitoring – analytics, compliance, alarms, health status







-----------------------------------------------------


Prism Element
++++++++

Less than 10 secs to determine if there’s need for action

.. figure:: images/PrismElement.png


The Home dashboard displays cluster-level performance and usage statistics on the left, health status info in the middle, and the most recent alert and event messages on the right.  The cluster name displays on the far left of the menu bar, next to the entity drop-down.

Prism is an end-to-end management solution for a virtualized datacenter, streamlining common hypervisor and VM tasks.

Focus is on common operational tasks in four areas:
Infrastructure management
Operational insight
Capacity planning
Performance monitoring





-----------------------------------------------------


Prism Element: Data Resiliency
++++++++

RF -> FT

.. figure:: images/PrismElementDataResiliency.png



-----------------------------------------------------


Command Line Interfaces
++++++++

References found on Portal

.. figure:: images/CommandLineInterfaces.png


Run system administration commands against a Nutanix cluster from:

- A local machine

- Any CVM in the cluster

Two CLIs:

- nCLI – Get status and configure entities within a cluster

- aCLI – Manage hosts, networks, snapshots and VMs the Acropolis portion of the Nutanix environment


Acropolis 5.5 Command Reference Guide

- Contains nCLI, aCLI and CVM commands

Remote system login (Downloaded nCLI): ncli -s management_ip_addr -u 'username' -p 'user_password'

General help: ncli> help
Entity help (e.g. containers): ncli> container help
Action help (e.g. creating a VM): ncli> vm create help






