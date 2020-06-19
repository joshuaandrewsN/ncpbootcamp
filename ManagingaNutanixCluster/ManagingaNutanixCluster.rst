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


Several methods to manage a Nutanix implementation:

-Graphical UI – Prism Element and Prism Central
  -Preferred method for management
  -Manage entire environment (when using Prism Central)

-Command Line Interfaces
  - nCLI – Get status and configure entities within a cluster
  - ACLI – Manage the Acropolis portion of the Nutanix environment

- Nutanix PowerShell Cmdlets – For use with Windows PowerShell

- REST API – Exposes all GUI components for orchestration and automation



-----------------------------------------------------


Prism Architecture
++++++++

Prism Element, Prism Central

.. figure:: images/PrismArchitecture.png




-----------------------------------------------------


Prism Element
++++++++

Less than 10 secs to determine if there’s need for action

.. figure:: images/PrismElement.png


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






