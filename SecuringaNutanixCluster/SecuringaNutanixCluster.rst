.. Adding labels to the beginning of your lab is helpful for linking to the lab from other pages
.. _Securing_a_Nutanix_Cluster_1:

--------------------------
Securing a Nutanix Cluster
--------------------------

Session 3

-----------------------------------------------------

STIG : Security Technical Implementation Guide
++++++++++++++++++++++++++++++++++++++++++++++++

.. figure:: images/stig.png

STIG Implementation - https://public.cyber.mil/stigs/

To make the STIGs usable by all organizations, the STIGs are provided in machine-readable XCCDF.xml format in addition to the human-readable PDF format.  This enables organizations to use tools that can read STIGs and automatically validate the security baseline of a deployment, reducing the accreditation time required to stay within compliance from months to days.


- Defines secure IT environment
- Security Configuration Management Automation (SCMA) monitors over 800 security entities

  - storage
  - virtualization
  - management

- XCCDF Support


-----------------------------------------------------

Encryption
++++++++++++++++++++++++++++++++

**Data-at-Rest Encryption: Self-encrypting Drives**

.. figure:: images/Encryption.png

- Self-encrypting Drives (SED) or software-enabled

- Requires external key management

- SEDs use FIPS 140-2 validated cryptographic mods

- A non-protected cluster can contain both SED and standard drives (DARE cannot be enabled)

- Each node maintains a set of certificates and keys in order to establish a secure connection with the key management server


-----------------------------------------------------

Encryption Part 2
++++++++++++++++++++++++++++++++

**Data-at-Rest Encryption: Software-based (no SEDs)**

.. figure:: images/Encryption2.png

- Uses AOS; no way to access the data directly from the drive

- DEK applied to data written to disk

- Data is encrypted at all times

- For empty or new clusters




-----------------------------------------------------

Client Authentication & Authorization
++++++++++++++++++++++++++++++++++++++

**Data-at-Rest Encryption: Software-based (no SEDs)**

.. figure:: images/clientauth.png

- Logons can require a combination of a client certificate and username and password

- Use local accounts or Active Directory/OpenLDAP

- SSL certificate-based authentication for console access: replace the default self-signed certificate with a CA signed certificate 

- Assign roles to users (Prism): User Admin, Cluster Admin, and Viewer





-----------------------------------------------------

Questions
++++++++++++++++++++++

This is a link to the Questions : :doc:`Questions`
