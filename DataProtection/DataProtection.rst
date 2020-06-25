.. Adding labels to the beginning of your lab is helpful for linking to the lab from other pages
.. _Data_Protection_1:

-----------------
Data Protection
-----------------

Session 10


-----------------------------------------------------

Inter-cluster Data Replication
++++++++++++++++++++++++++++++++

**Based on e.g. RPO and RTO considerations**

.. figure:: images/Inter-clusterDataReplication.png

Picking the right solution always involves trade-offs. While a remote site is not your datacenter, uptime is nonetheless a crucial concern. Financial constraints and physical layout also affect what counts as the best architecture for your environment. Nutanix offers a wide variety of clusters for remote locations. You can select single- and dual-socket cluster options, as well as options that can reduce licensing costs.

Remote sites are a logical construct. Admins must first configure any Acropolis cluster—either physical or cloud based—that functions as the snapshot destination and as a remote site from the perspective of the source cluster. Similarly, on this secondary cluster, configure the primary cluster as a remote site before snapshots from the secondary cluster start replicating to it. Configuring backup on Nutanix lets an organization use its remote site as a replication target. You can back up data to this site and retrieve snapshots from it to restore locally, but you can’t enable failover protection (running failover VMs directly from the remote site). Backup also supports using multiple hypervisors. For example, an enterprise might have ESXi in the main datacenter but use Hyper-V at a remote location. With the backup option configured, the HyperV cluster could use storage on the ESXi cluster for backup. Using this method, Nutanix can also back up to AWS from Hyper-V or ESXi.

**Recovery Point Objective (RPO):**

- Tolerated time interval after disruption that allows for a quantity of data lost without exceeding the maximum allowable threshold.

  - RPO designates the variable amount of data that will be lost or will have to be re-entered during network downtime.

    - Example: If the data snapshot interval and the RPO is 180 minutes, and the outage lasts only 2 hours, you’re still within the parameters that allow for recovery and business processes to proceed given the volume of data lost during the disruption.

**Recovery Time Objective (RTO):**

- How much time does it take to recover after notification of business process disruption?


  - RTO is therefore the duration of time and a service level within which a business process must be restored after a disaster in order to avoid unacceptable consequences associated with a break in continuity.

  - RTO designates the amount of “real time” that can pass before the disruption begins to seriously and unacceptably impede the flow of normal business operations.

**RPO and RTO considerations:**

- Time Stream and Cloud: High RPO and RTO (hours), used for minor incidents.
- Synchronous and Asynchronous: (Near)-Zero RPO and RTO, used for major incidents.





-----------------------------------------------------

References
+++++++++++++++++++++++++

-----------------------------------------------------

.. figure:: images/FailureandScenarios.png

`Failure and Scenarios <https://portal.nutanix.com/page/documents/details/?targetId=Web-Console-Guide-Prism-v5_15:arc-failure-modes-c.html>`_
""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""

-----------------------------------------------------

.. figure:: images/VMHighAvailabilityinAcropolis.png

`VM High Availability in Acropolis <https://portal.nutanix.com/page/documents/details/?targetId=Web-Console-Guide-Prism-v5_15:wc-high-availability-acropolis-c.html>`_
""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""

-----------------------------------------------------

.. figure:: images/DataProtectionandDisasterRecovery.png

`Data Protection and Disaster Recovery <https://www.nutanix.com/go/enterprise-cloud-data-protection-on-nutanix>`_
""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""

-----------------------------------------------------

.. figure:: images/DefinitiveGuidetoDataProtectionandDisasterRecovery.png

`Definitive Guide to Data Protection and Disaster Recovery <https://www.nutanix.com/go/the-definitive-guide-to-data-protection-and-disaster-recovery-on-enterprise-clouds>`_
""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""


-----------------------------------------------------

.. figure:: images/RedundancyFactorvsReplicationFactor.png

`Redundancy Factor vs. Replication Factor <https://www.youtube.com/watch?v=tVPhl52thDY>`_
""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""


-----------------------------------------------------

.. figure:: images/InfrastructureResiliency.png

`Infrastructure Resiliency <https://www.nutanix.com/go/nutanix-converged-infrastructure-system-reliability>`_
""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""


-----------------------------------------------------

.. figure:: images/DataProtectionandDisasterRecoveryBook.png

`Data Protection and Disaster Recovery <https://www.nutanix.com/go/data-protection-and-disaster-recovery-on-nutanix>`_
""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""""



-----------------------------------------------------

Questions
++++++++++++++++++++++

This is a link to the Questions : :doc:`Questions`


