.. title:: Nutanix NCP Bootcamp

.. toctree::
  :maxdepth: 2
  :caption: Sessions
  :name: _labs
  :hidden:

  NutanixConcepts/NutanixConcepts
  ManagingaNutanixCluster/ManagingaNutanixCluster
  SecuringaNutanixCluster/SecuringaNutanixCluster
  Networking/Networking
  VMCreationandManagement/VMCreationandManagement
  HealthMonitoringandAlerts/HealthMonitoringandAlerts
  DistributedStorageFabric/DistributedStorageFabric
  AcropolisStorageServices/AcropolisStorageServices
  DataResiliancy/DataResiliancy
  DataProtection/DataProtection
  PrismCentral/PrismCentral
  ClusterMaintenenceandLifecycleOperations/ClusterMaintenenceandLifecycleOperations

.. toctree::
  :maxdepth: 2
  :caption: Optional Questions
  :name: _optional_labs
  :hidden:

  OptionalQuestions/OptionalQuestions

.. toctree::
  :maxdepth: 2
  :caption: Appendix
  :name: _appendix
  :hidden:

  appendix/glossary
  appendix/otherstuff

.. _getting_started:

---------------
Getting Started
---------------

Welcome to the Nutanix NCP Bootcamp.  This short workshop is intended to provide a highlight of the NCP exam including breifly dicussing the objectives covered by the exam. 
At the end of the workshop you will know how to sign up to the exam, be armed with the testing details, have a solid overview of the topics on the exam and be familiar with the question format.


Agenda
++++++

- Introductions
- Nutanix Certified Professional Overview
- Nutanix Concepts
- Managing a Nutanix Cluster
- Securing a Nutanix Cluster
- Networking
- VM Creation and Management
- Health Monitoring and Alerts
- Distributed Storage Fabric
- Acropolis Storage Services
- Data Resiliancy
- Data Protection
- Prism Central
- Cluster Maintenence and Lifecycle Operations

Introductions
+++++++++++++

- Name
- Familiarity with Nutanix




Objectives
+++++++++++++

ECA refresh 
Practice questions
- Test knowledge
- Question layout and standards
- Get into the exam mindset


Exam Details
+++++++++++++++++++

The NCP exam consists of 75 questions covering twelve sections with a timelimit of 120 minutes.
The exam normally requires at least 24 hours advanced scheduling and is remote-proctored.

Exam Blueprint Guide
..........

The Exam Blueprint Guide, available in the NCP learning plan at NutanixUniversity or in the Certifications page at nutanix.com, lists all of the pertinent information about the exam.

.. figure:: images/ebg.png

The Exam Blueprint Guide lists the security policies in place and the intended audience:

.. figure:: images/ebgaud.png

A key resource on the EBG is the list of objectives the exam covers including references. You should be familiar with the technologies and features described as well as the references listed.

 .. figure:: images/ebgsections.png



Hosted POC clusters follow a standard naming convention:

- **Cluster Name** - POC\ *XYZ*
- **Subnet** - 10.**21**.\ *XYZ*\ .0
- **Cluster IP** - 10.**21**.\ *XYZ*\ .37

If provisioned from the marketing pool:

- **Cluster Name** - MKT\ *XYZ*
- **Subnet** - 10.**20**.\ *XYZ*\ .0
- **Cluster IP** - 10.**20**.\ *XYZ*\ .37

For example:

- **Cluster Name** - POC055
- **Subnet** - 10.21.55.0
- **Cluster IP** - 10.21.55.37

Throughout the Workshop there are multiple instances where you will need to substitute *XYZ* with the correct octet for your subnet, for example:

.. list-table::
   :widths: 25 75
   :header-rows: 1
   * - IP Address
     - Description
   * - 10.21.\ *XYZ*\ .37
     - Nutanix Cluster Virtual IP
   * - 10.21.\ *XYZ*\ .39
     - **PC** VM IP, Prism Central
   * - 10.21.\ *XYZ*\ .40
     - **DC** VM IP, NTNXLAB.local Domain Controller

Each cluster is configured with 2 VLANs which can be used for VMs:

.. list-table::
  :widths: 25 25 10 40
  :header-rows: 1
  * - Network Name
    - Address
    - VLAN
    - DHCP Scope
  * - Primary
    - 10.21.\ *XYZ*\ .1/25
    - 0
    - 10.21.\ *XYZ*\ .50-10.21.\ *XYZ*\ .124
  * - Secondary
    - 10.21.\ *XYZ*\ .129/25
    - *XYZ1*
    - 10.21.\ *XYZ*\ .132-10.21.\ *XYZ*\ .253

Credentials
...........

.. note::

  The *<Cluster Password>* is unique to each cluster and will be provided by the leader of the Workshop.

.. list-table::
   :widths: 25 35 40
   :header-rows: 1
   * - Credential
     - Username
     - Password
   * - Prism Element
     - admin
     - *<Cluster Password>*
   * - Prism Central
     - admin
     - *<Cluster Password>*
   * - Controller VM
     - nutanix
     - *<Cluster Password>*
   * - Prism Central VM
     - nutanix
     - *<Cluster Password>*

Each cluster has a dedicated domain controller VM, **DC**, responsible for providing AD services for the **NTNXLAB.local** domain. The domain is populated with the following Users and Groups:

.. list-table::
   :widths: 25 35 40
   :header-rows: 1
   * - Group
     - Username(s)
     - Password
   * - Administrators
     - Administrator
     - nutanix/4u
   * - SSP Admins
     - adminuser01-adminuser25
     - nutanix/4u
   * - SSP Developers
     - devuser01-devuser25
     - nutanix/4u
   * - SSP Consumers
     - consumer01-consumer25
     - nutanix/4u
   * - SSP Operators
     - operator01-operator25
     - nutanix/4u
   * - SSP Custom
     - custom01-custom25
     - nutanix/4u
   * - Bootcamp Users
     - user01-user25
     - nutanix/4u

Access Instructions
+++++++++++++++++++

The Nutanix Hosted POC environment can be accessed a number of different ways:

Lab Access User Credentials
...........................

PHX Based Clusters:
**Username:** PHX-POCxxx-User01 (up to PHX-POCxxx-User20), **Password:** *<Provided by Instructor>*

RTP Based Clusters:
**Username:** RTP-POCxxx-User01 (up to RTP-POCxxx-User20), **Password:** *<Provided by Instructor>*

Frame VDI
.........

Login to: https://frame.nutanix.com/x/labs

**Nutanix Employees** - Use your **NUTANIXDC** credentials
**Non-Employees** - Use **Lab Access User** Credentials

Parallels VDI
.................

PHX Based Clusters Login to: https://xld-uswest1.nutanix.com

RTP Based Clusters Login to: https://xld-useast1.nutanix.com

**Nutanix Employees** - Use your **NUTANIXDC** credentials
**Non-Employees** - Use **Lab Access User** Credentials

Employee Pulse Secure VPN
..........................

Download the client:

PHX Based Clusters Login to: https://xld-uswest1.nutanix.com

RTP Based Clusters Login to: https://xld-useast1.nutanix.com

**Nutanix Employees** - Use your **NUTANIXDC** credentials
**Non-Employees** - Use **Lab Access User** Credentials

Install the client.

In Pulse Secure Client, **Add** a connection:

For PHX:

- **Type** - Policy Secure (UAC) or Connection Server
- **Name** - X-Labs - PHX
- **Server URL** - xlv-uswest1.nutanix.com

For RTP:

- **Type** - Policy Secure (UAC) or Connection Server
- **Name** - X-Labs - RTP
- **Server URL** - xlv-useast1.nutanix.com


Nutanix Version Info
++++++++++++++++++++

- **AHV Version** - AHV 20170830.337
- **AOS Version** - 5.11.2.3
- **PC Version** - 5.11.2.1
