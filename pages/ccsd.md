---
layout: ccsd
title: Services
permalink: /ccsd/
---
<!--<style>
    table {
        border-collapse: collapse;
        border-spacing: 0;
        border:2px solid #ff0000;
    }

    th {
        border:2px solid #000000;
    }

    td{
        border:1px solid #000000;
    }
</style>
-->

#Cloud Computing Services Description (CCSD)##
_Extracted from FCS SIR J-1, dated August 21, 2015_

_Please refer to the hardcopy on the FCS CO SharePoint for the cannonical verbiage_

<!---
## 1. Introduction

### 1.1 Purpose
This document describes the technical requirements for the services that the
Federal Aviation Administration (FAA) will acquire under the FAA Cloud
Services (FCS) contract. The principal service commodities are “cloud
computing services” that may be used to support the development,
testing, operation, and support of National Airspace System (NAS)
subsystems and tenant applications as well as FAA Administrative and
Mission Support systems and applications. This document also describes
the technical requirements for Colocation services to host FAA IT
equipment, and automated capabilities such as account management,
performance monitoring, and security operations that must be provided to
support the delivery of the required computing services.

### 1.2 Definition of Key Terms
The following terms are used throughout this document to describe the
FAA’s requirements for computing services. The terms are defined here to
ensure a common understanding of the requirements.

|  **Term**                                |  **Description**
|  ----------------------------------------|--------------------------------------------------------------------------------------------------|
|  Archived Off-line Storage               |    Off-line storage used for long-term storage of tenant application data. The tenant cannot read/write directly to archive storage.
|  Bundled Storage                         |    Network storage that is included (i.e., bundled) with the VM or non-VM. Bundled storage may correspond to “local” storage (i.e., on the same physical server on which the tenant application is running) or networked storage as long as it conforms to the performance specifications. The term “bundled” is used to differentiate this storage from additional networked storage that may be optionally ordered as a supplemental feature.
|  Cloud Computing Service                 |    The basic units of service to be obtained under this contract. Cloud Computing services will be ordered in terms of “service classes” that define a specific amount of computing resources to be allocated (virtually or physically) to the user along with the associated performance specifications.
|  Colocation Service                      |    The basic unit of service that may be ordered under this contract. A Colocation Service corresponds to environmentally controlled physical space (including cabinets/racks, power, cooling, and cabling) provided by the Contractor at their premises to host Government-owned and operated IT assets. The space must be a physically separate area accessible only by authorized personnel. Colocation Services will be ordered in terms of square footage of floor space and the number of cabinets/racks. As supplemental features specific to Colocation Services, the Government may optionally order local hardware support, monitoring as a service, management of removable storage media, and networked storage.
|  Computing Infrastructure                | The hardware (e.g., servers, processors, communications networks, storage devices, security appliances, other peripherals, etc.) and software (e.g., operating systems, applications programming interfaces, directory services, utilities, etc.) comprising a physical computing environment.
|  Core                                    | The basic unit of processing capacity. (Previously called Central Processing Unit (CPU). Manufacturers typically integrate multiple cores onto a single [integrated circuit](https://en.wikipedia.org/wiki/Integrated_circuit) [die](https://en.wikipedia.org/wiki/Die_%28integrated_circuit%29) (known as a Chip Multiprocessor or CMP), or onto multiple dies in a single [chip package](https://en.wikipedia.org/wiki/Chip_carrier).)
|  Elasticity                              | An optionally ordered supplemental feature in which computing resources can be dynamically allocated and de-allocated to a Virtualized Machine (VM) service. Elastic use of computing resources enables a VM service to temporarily use additional computing resource beyond the base-level specifications of the associated service class. Elasticity does not apply to non-VMs.
|  FedRAMP Compliant                       | CSPs providing cloud computing services are considered FedRAMP compliant if their cloud systems (Private, Government Community, and Public Cloud) meet these criteria:
|                                          | 1.  Implemented FedRAMP moderate baseline security controls within their existing cloud computing infrastructure that is offering services to government customers;
|                                          | 2.  Assessed by an accredited 3PAO to independently validate and verify that the CSP cloud computing infrastructure meets the FedRAMP requirements for moderate baseline security controls;
|                                          | 3.  Completed all FedRAMP security assessment templates;
|                                          | 4.  Authorization letters are on file with the FedRAMP PMO and the system security package is listed in the FedRAMP repository.
|  Government Community Cloud              | The physical computing environment is provisioned for exclusive use by the community of tenants from U.S. government agencies that have shared requirements. It is hosted at the Cloud provider’s facilities.
|  Logical Separation                      | Acceptable logical separation includes Virtual Local Area Networks, fiber channel switching zones, Multiprotocol Label Switching, virtualization platforms, and other mechanisms as approved by the Government.
|  Monitoring and Control                  | Monitoring is maintaining an awareness of the state of a system. It is a “read-only” function. Control is a “read/write” function. It is the ability to power systems up and down, reboot them,  provisioning services, and change their configurable operating parameters (not their actual physical configurations. i.e., adding or removing cards).
|  Non-Virtualized Machine                 | The allocation of specific and dedicated physical computing resources or servers as the run-time environment for a particular tenant application.
|  Non-Cloud Tenant Applications           | A non-cloud tenant application runs in an FAA owned or third party data center that is separate from an FCS-provided computing infrastructure. The FAA may order a service (e.g.., Remote Storage Service) that can be utilized by non-cloud tenant applications.
|  On-Demand Service                       | A service that receives its allocation of computing resources on an as-requested basis. When an on-demand service is not in a running state, the associated computing resources are de-allocated. The cost of the service is based on actual usage of computing resources (i.e. the amount of time it is in a running state). An on-demand service can be viewed as the opposite of a persistent service.
|  Operating Domain                        | A grouping of tenant applications that share a common wide area network connectivity, security controls, and protections. The FCS encompasses eleven operating domains: NAS Private Operational Domain, NAS Private Operational Test Domain, Admin/Mission Support Private Operational Domain, Admin/Mission Support Private Operational Test Domain, NAS Government Community Development/Test Domain, Admin/Mission Support Government Community Operational Domain, Admin/Mission Support Government Community Operational Test Domain, Admin/Mission Support Government Community Development/Test Domain, Public Web Services Domain, Admin/Mission Support Colocation Operational Domain, and NAS Colocation Operational Domain. Operating domains within the same physical computing environment require logical separation.
|  Persistent Service                      | A service that retains its allocation of computing resources corresponding to the base-level specification of its associated service class when it is ordered. From the point the service is provisioned until the service is discontinued, it retains its base level of resources (e.g. cores, Random Access Memory (RAM), bundled storage). By definition, all non-virtual machine services are persistent. Through the use of elasticity, a Virtual Machine (VM) service may exceed its base allocation of computing resources, but the allocation of computing resources to a persistent VM service will not fall below the base allocation.
|  Physical Computing Environment          | A set of physical computing infrastructure that is physically or logically separated from other sets of computing infrastructure for the exclusive use by a particular group of applications. The FCS has six physical computing environments: NAS Private Cloud, Admin/Mission Support Private Cloud, Government Community Cloud, Public Cloud, Admin/Mission Support Colocation, and NAS Colocation. Each physical computing environment contains one or more Operating Domains. The operating domains within a particular physical computing environment do not require physical separation. At a minimum, the NAS Private, Admin/Mission Support Private, NAS Colocation, and Admin/Mission Support Colocation must be physically separated from each other and any other computing infrastructures.  At a minimum, the Government Community Cloud and the Public Cloud must be logically separated from each other and any other computing infrastructures. 
|  Physical separation                     | Entities requiring physical separation must not share physical equipment/component, network switches, cables, cabinets/racks, and other mechanisms as approved by the Government.
|  Private Cloud                           | The physical computing environment is provisioned for exclusive use by FAA tenants only. It is hosted at the Cloud provider’s facilities.
|  Public Cloud                            | The physical computing environment is provisioned for open use by the general public. It is hosted at the Cloud provider’s facilities.
|  Real-time                               | Implies the data is immediately available (with minimal latency) from the point at which the data values are collected and/or the data values are calculated.
|  Recovery Point Objective (RPO)          | The point in time measured in hours or minutes that the FCS provider must have the data available and in the same state. Example: If the disaster occurred at 3pm EST, and the disaster recovery level is a four hour RPO, the data must be at the same state as it was at 11am EST.
|  Recovery Time Objective (RTO)           | The amount of time in hours or days that the FCS provider must have the service recovered after a disaster. The RTO clock starts at the point of service interruption and ends when the service is restored at the alternate or standby data center facility.
|  Remote Storage                          | Network storage that can be accessed, when ordered as a service, by non-Cloud tenant applications via a remote storage management agent, command line interface, or a web browser.
|  Self-Service Provisioning               | A consumer can unilaterally provision computing capabilities, such as server time and network storage, as needed without requiring human interaction with each service’s provider. This capability is provided via the On-Line User Interface.
|  Service                                 | Refers to an instance, or occurrence, of a service class (e.g., a specific Virtual Machine instantiated for a tenant application).
|  Service Acceptance                      | The Government’s formal acceptance of a cloud computing service based upon the Contractor’s demonstration that a particular service class instantiation meets the associated performance specifications. A service is considered to be “in-service” from the point of Service Acceptance until Service Discontinuation.
|  Service Class                           | The distinct orderable commodities of the cloud computing service defined in terms of the number of cores, RAM, storage, and service availability. Basic cloud computing services may be augmented with optionally ordered supplemental features.
|  Service Discontinuation                 | The Government’s formal discontinuation of a cloud computing service after service acceptance and/or usage. It is the point at which billing for the service must stop regardless of whether the contractor has actually de-allocated the resources associated with the service.
|  Supplemental Features                   | Additional services that are optionally ordered in conjunction with an individual service. Examples of supplemental features include: operating systems, elasticity, and disaster recovery.
|  Tenant Application                      | Software and data that is deployed and run at Contractor-provided or Government-provided physical computing environments. The Tenant Application is the *user* of a computing service.
|  Tier III “Self” Certified facility      | The contractor provides evidence that the facility meets or exceeds the Tier III “Concurrently maintainable site infrastructure” topology standard from the Uptime Institute. A sub-set of the Uptime Institute facility requirements for self-certification is listed in Appendix A - Tier III Facility Standards: Checklist for self-certification.
|  Virtual Machine (VM)                    | An emulation of a computing infrastructure in which requests for CPU, memory, hard disk, network and other hardware resources are managed by a virtualization layer that translates these requests to the underlying physical hardware. VMs can be ordered with or without the operating system. When ordered without the operating system, the Government is responsible for providing the operating system. When ordered with the operating system, the Government will specify the operating system and the Contractor will be responsible for providing and maintaining it.
|  VM snapshot                             | Captures the state, configuration, and data of a running virtual machine at a specific point in time.

### 1.3 Document Organization
Section 1 states the purpose and scope of this document. It also defines
terminology that provides the basis for consistent references in the
description of the service requirements.

Section 2 defines the applicable reference documents cited in this
specification.

Section 3 specifies the performance requirements for FCS computing
services and supplemental features.

Section 4 defines the specific physical computing environment and
operating domains that must be supported and the security requirements
that apply to each operating domain.

Section 5 defines the network interface requirements that govern local
area network connections, wide area network connections, and connections
to the Internet.

Section 6 defines the service classes that the FCS must support for
virtualized machines, non-virtualized computing resources, colocation
services, on-line network storage, and other services.

Section 7 defines the requirements for supplemental features that may be
optionally ordered.

Section 8 contains the monitoring and control requirements with respect
to the operating domains and tenant applications.

Section 9 contains the requirements for on-line user interfaces that
must be provided to support account management, visibility into the
real-time performance of the operating domains and tenant applications,
and the security posture of the operating domains.

# 2. Applicable Documents
The following documents are cited in other sections of this CCSD. They
are the sources of additional requirements that apply to the FCS
computing services. The current version of each document is identified.
If an applicable document is updated during the contract period of
performance, the contract will be modified to cite the latest version.
The Contractor must adhere to the latest version of each document.  When
an applicable document is updated, the Contractor must identify any
impact to the performance, cost, schedule, etc. or other factors
affecting the delivery of FCS computing services. The Government will
review the Contractor's impact assessment and determine if a contract
modification is required.

### 2.1 Government Documents

#### 2.1.1 FAA Orders

|  **Doc No.**          |  **Document Title**                                         |  **Version / Date**     |  **Sections**
|  -------------------- |  ---------------------------------------------------------- |  --------------------   |  --------------
|  FAA Order 1370.106   |  Information Systems Security Awareness & Training Policy   |  June 16, 2009          |
|  FAA Order 1600.1E    |  Personnel Security Program                                 |  July 25, 2005          |
|  FAA Order 1600.72A   |  Contractor and Industrial Security Program                 |  December 28, 2005      |

#### 2.1.2 Other FAA Documents

|  **Doc No.**          |  **Document Title**                                         |  **Version / Date**     |  **Sections**
|  ---------------------|-------------------------------------------------------------|-------------------------|--------------
|  FTSD                 |  FAA Telecommunications Services Description (FTSD)         |  Up through Modification P0052  |  3.0 through 6.0
|  FTI ED8 External Users’ Guide  |  FTI Enterprise Security Gateway Users’ Guide – Volume II – For Non-NAS Users  | Revision 2c, Feb 2010

#### 2.1.3 Other Government Documents

|  **Doc No.**          |  **Document Title**                                         |  **Version / Date**     |  **Sections**
|  ---------------------|-------------------------------------------------------------|-------------------------|--------------
|  NIST Special Publication 800-53  | Security and Privacy Controls for Federal Information Systems and Organizations                                   |   Revision 4
|  NIST Special Publication 800-37  | Guide for Applying the Risk Management Framework to Federal Information Systems – A Security Life Cycle Approach  |   Revision 1 February 2010
|  OMB M-08-05                      | Implementation of Trusted Internet Connections (TIC)                                                              |  Nov. 20, 2007
|  NIST SP 800-137,                 | Information Security Continuous Monitoring for Federal Information Systems and Organization                       | Version 1.0 July 27, 2012
|  OMB Memorandum                   | FedRAMP Policy Memo: Security Authorization of Information Systems in Cloud Computing                             | Dec. 8, 2011
|  FedRAMP                          | FedRAMP Baseline Security Controls Version 4                                                                      | July 25, 2012
|  DOT Order 1351.37                | DOT Cyber Security Policy Order and DOT Cyber Security Compendium Version 3
  ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

### 2.2 Non-Government Documents
|  **Doc No.**          |  **Document Title**                                         |  **Version / Date**     |  **Sections**
|  ---------------------|-------------------------------------------------------------|-------------------------|--------------
|  ISO/IEC 7498-1       |  OSI Model
|  SPECsfs2008          |  SPECsfs2008\_nfs.v3 and SPECsfs2008\_cifs server performance benchmarks
|  SPECint2006          |  SPECint2006\_x CPU’s integer performance benchmarks        |
|  Uptime Institute, LLC|  Data Center Site Infrastructure Tier Standard: Topology    |August 1, 2012
|  Uptime Institute, LLC|  Data Center Site Infrastructure Tier Standard: Operational Sustainability   | April 1, 2013
|  www.section508.gov   |  Section 508 Reference Manual
|  World Wide Web Consortium  |Web Content Accessibility Guidelines (WCAG) 2.0

### 2.3 Order of Precedence
When the requirements of this document and referenced applicable documents are in conflict, this document has precedence over all documents referenced herein. If two or more referenced applicable documents are in conflict or two or more sections of this document are in conflict, the FAA Contracting Officer must be notified to resolve the conflict.

### 2.4 Availability of Documents

#### 2.4.1 FAA Documents
Copies of FAA specifications, standards, and publications are available
via the FCS Procurement Web Portal described in Section L.
Alternatively, these materials may be obtained from the FCS Contracting
Officer, FAA, William J. Hughes Technical Center, and Atlantic City
International Airport, NJ  08405; or by emailing <FCS-SIR@faa.gov>.
Requests should clearly identify the desired material by number and
state the intended use of the material.

#### 2.4.2 International Civil Aviation Organization (ICAO) Documents
Copies of ICAO documents may be obtained from the ICAO Library, 999
University Street, Montreal, Quebec H3C 5H7, Canada.

_**Note:** For current working documents that are not final products,
inquire at ICAO website
http://www.icao.int/anb/panels/acp/repository.cfm._

#### 2.4.3 International Organization for Standardization (ISO) Documents
Copies of ISO documents may be obtained from ISO Central Secretariat, 1,
ch. de la Voie-Creuse, Case postale 56, CH-1211 Geneva 20 Switzerland,
by phone +41 22 749 01 11, or through the website
http://www.iso.org/iso/en/ISOOnline.frontpage.

#### 2.4.4 Internet Engineering Task Force (IETF) Documents
Copies of Internet Engineering Task Force documents may be obtained
through the website: <http://www.ietf.org>.

#### 2.4.5 Uptime Institute
Copies of the Uptime Institute documents may be obtained through the
website: <http://uptimeinstitute.com/>

#### 2.4.6 NOAAPORT
Information on NOAAPORT may be obtained through the website:
<http://www.nws.noaa.gov/noaaport/html/noaaport.shtml>

#### 2.4.7 Electronic Industries Association (EIA) - 310
Copies of the EIA documents can be obtained through the website:
http://www.ecianow.org

#### 2.4.8 National Institute of Standards and Technology (NIST) Documents
Copies of National Institute of Standards and Technology documents may
be obtained through the website:
<http://csrc.nist.gov/publications/PubsSPs.html>.

#### 2.4.9 Standard Performance Evaluation Corporation (SPEC)
Copies of the SPEC documents can be obtained through the website:
[www.spec.org](http://www.spec.org)

#### 2.4.10 Internet Protocol v6
Copies of the IPv6 specification can be obtained through the website:
<http://www.ietf.org/rfc/rfc2460.txt>

#### 2.4.11 Federal Risk and Authorization Management Program (FedRAMP)
Copies of the FedRAMP documents can be obtained through the website:
[www.fedramp.gov](http://www.fedramp.gov)

#### 2.4.12 Other Federal Government Documents
Copies of federal publications may be obtained from the U.S. Government
Printing Office, 710 North Capitol Street, Washington DC, 20401, or by
calling (202) 512-0132, or through the website
<http://bookstore.gpo.gov/>.

-->

## 3. Performance Requirements
This section defines performance parameters and requirements that form
the basis for defining the required service classes in Section 6 of this
document. Unless otherwise stated for a particular class of services,
the Contractor is responsible for:

1. All aspects of service quality, security, and interoperability.
2. Delivering all services at the required performance levels as specified in this document.
3. Meeting the specified performance regardless of service usage levels of the computing infrastructure or service classes.

The performance requirements for FCS are defined in terms of the
Reliability, Maintainability, Availability (RMA), and performance for
processing capacity, RAM, storage, remote storage, and network
throughput. This section also includes performance requirements for
additional services that may be ordered as supplemental features in
association with a particular service class.

### 3.1 Reliability
Reliability is defined in terms of a service’s ability to perform within
a specified outage limit over a prescribed period of time and to achieve
a particular level of continuous “up time” between outages. The outage
limit and Mean Time Between Outages (MTBO) requirements in this section
apply to each service class on an individual basis.

An *outage* is defined as the condition in which a service is
unavailable for operational use by the designated tenant application or
the service fails to meet all applicable performance requirements
defined in this document for the associated service class. If a
supplemental feature ordered in conjunction with a particular service is
unavailable or is not meeting its performance specifications, it also
constitutes an outage of the associated service. Local area network
connectivity as defined in CCSD Section 5.1 and inter-process
communications as defined in CCSD Section 5.4 must support the
availability levels of the services using those capabilities. Loss of
Contractor-provided local area network connectivity or inter-process
communications capabilities represents an outage of services that depend
upon those capabilities.

The maximum number of outages for each instance of each service class
allowed in a 12-month period is listed in Table 3-1 for each performance
level. A service interruption due to a Government-ordered supplemental
feature added to an existing service does not count as an outage unless
the change is not completed within the required timeframe as specified
in Section F.8.4 of the contract.

**Table 3‑1 Maximum Number of Outages by Performance Level**

|**Parameter**                                                      |   **Level\_1**|  **Level\_2** |  **Level\_3**
|-----------------------------------                                |---------------|---------------|-----------
|  Maximum Number of Outages (most recent 12-month period)          |  6            |  6            |  6

In addition to the maximum number of outages, the MTBO must be no less
than the values listed in Table 3‑2.

**Table 3‑2 Mean Time between Outages by Performance Level**
|**Parameter**                                                      |   **Level\_1**|  **Level\_2** |  **Level\_3**
|-----------------------------------                                |---------------|---------------|-----------
|  MTBO (in hours)                                                  |  1560.0       |  1560.0       |  1560.0

The measurement and reporting of the MTBO must be based upon the most
recent 12-month period or the total time in-service for services that
have been in-service for less than 12 months. The MTBO must be
calculated as follows:

*Maximum\_In-Service\_Time (hr) – Total\_Outage\_Time (hr)*

*Number\_of\_Service\_Outages*

where:

Maximum\_In-Service\_Time = The maximum of the Total In-Service Time
during the most recent 12-month period **or** since the service was
accepted but not yet discontinued. Periods of time during which a
service is not in use by a tenant application count as in-service time
provided that the service is available for use. The
"Maximum\_In\_Service\_Time" is (24 hours per day) x (number of days in
a year).

Total\_Outage\_Time = Total time during the Maximum\_In-Service\_Time
period that the service was not available for operational use by the
Government or failed to meet all applicable performance requirements
defined in this document. The Total\_Outage\_Time includes any outage
time attributable to preventive maintenance that makes the service
unavailable for operational use by the Government. Any portion of time
that a service is unavailable due to a Government-ordered service
upgrade does not count as outage time unless the upgrade is not
completed with the required timeframe as specified in Section F of this
contract.

> Number\_of\_Service\_Outages = Total number of outages incurred by a
> service during the Maximum\_In-Service\_Time period.

### 3.2 Availability
--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

The availability requirements in this section apply to each service
class on an individual basis. A service is defined as being “in-service”
from the point at which it passes Service Acceptance through Service
Discontinuation. The availability of a FCS service is measured in
calendar month increments and must be calculated as follows:

*Maximum\_In-Service\_Time) *

*Maximum\_In-Service\_Time + Total\_Outage\_Time (hr)*

where:

Maximum\_In-Service\_Time = Total In-Service Time during the calendar
month. For newly accepted services, the In-Service Time begins when the
service is accepted. For discontinued services, the Service Time ends as
of the effective date of the Discontinue order. Periods of time during
which a service is not in use by a tenant application count as
in-service time provided that the service is available for use.

Total\_Outage\_Time = Total time during the Maximum\_In-Service\_Time
period that the service was not available for operational use by the
Government or failed to meet all applicable performance requirements
defined in this document. The Total\_Outage\_Time includes any outage
time attributable to preventive maintenance that makes the service
unavailable for operational use by the Government.

Each service class must meet or exceed the minimum availability
specified in Table 3‑3 for its associated performance level for each
calendar month and the most recent 12-month period. If a service has
been in-service for less than 12 months, its 12-month availability is
“Not Applicable”

Table 3‑3 Minimum Availability by Performance Level

  **Parameter**          **Level\_1**   **Level\_2**   **Level\_3**
  ---------------------- -------------- -------------- --------------
  Minimum Availability   99.98%         99.9%          98.5%

### 3.3 Service Restoral / Maintainability

In the event of an outage, service classes must be restored within the
time limits defined in Table 3‑4.

Table 3‑4 Maximum Restoration Time by
Performance Level

  **Parameter**              **Level\_1**   **Level\_2**   **Level\_3**
  -------------------------- -------------- -------------- -----------------
  Maximum Restoration Time   20 minutes     90 minutes     24 hours, NBD\*

> \**NBD corresponds to the time on, the Next Business Day (NBD). *

For Next Business Day (NBD) restoration, intervening non-working days
are counted as “customer time” and are excluded from the restoration
time.

In those instances where a “service release” must be obtained per the
conditions in Performance Work Statement (PWS) paragraph C.4.5.3, the
time from the release request to when the release is granted by the
Government is excluded from the calculation of the actual Restoration
Time.

### 3.4 Computing and Storage

The following subsections identify the range of computing and storage
capabilities that must be available when ordered for individual service
classes. All services must support the ordered levels of service on a
continual basis.

#### 3.4.1 Processing

A *core* is the basic unit of processing capacity. The FCS service
classes for Virtual Machines must be available in variants of 1, 2, 4,
8, and 16 cores. The FCS service classes for Non-Virtual Machines must
be available in variants of 4, 8, 16, 32, and 64 cores. The FCS cores
must be based upon a 64-bit processing architecture. The FCS cores must
support emulation of a 32-bit processing architecture.

Each service class must meet or exceed the corresponding performance
levels listed in Table 3‑5 based on the associated number of cores. The
performance levels are defined as ratios of the performance attained by
the FCS divided by the performance attained by the reference processor
defined by the associated SPEC CPU2006 benchmarks. Processing Speed is
defined in terms of the amount of time it takes the processor to
complete a single unit of workload. Processing Throughput is defined as
the amount of workload that can be completed in a particular unit of
time. The greater the ratio value, the better the performance. The
service must meet or exceed all four ratio values to be considered in
compliance with the performance specification.

Table 3‑5 Minimum Processing Performance Levels

                    **Processing Speed Integer Computations**   **Processing Throughput Integer Computations**   **Processing Speed Floating Point Computations**   **Processing Throughput Floating Point Computations**
  ----------------- ------------------------------------------- ------------------------------------------------ -------------------------------------------------- -------------------------------------------------------
  **Benchmark**     SPECint\_base2006                           SPECint\_rate\_base2006                          SPECfp\_base2006                                   SPECfp\_rate\_base2006
  **\# of Cores**   **Minimum Ratios**
  1                 18.5                                        18.3                                             14.8                                               14.8
  2                 18.4                                        33.8                                             14.7                                               27.3
  4                 18.4                                        55.7                                             14.7                                               43.3
  8                 18.1                                        75.2                                             14.6                                               51.5
  16                18.2                                        95.0                                             14.6                                               55.0
  32                18.1                                        114.95                                           14.5                                               58.9
  64                18.0                                        139.0                                            14.5                                               63.0

#### 3.4.2 Random Access Memory

Random Access Memory (RAM) is the volatile memory in which tenant
applications reside and are executed. RAM includes space for data
structures defined by tenant applications to support their real-time
processing. RAM must be provided bundled with a service class or as
supplemental features. The performance of the RAM must support the
overall processing performance levels specified in Table 3‑5.

#### 3.4.3 Network Input/Output (I/O) Bandwidth

The FCS must support the Network I/O bandwidth rates specified in
association with each service class. The Network I/O bandwidth rates are
defined in terms of the total transfer rate in bits per second available
and does not take latency into account. The minimum bandwidth per
virtual machine instance is 100 Mbps. The minimum bandwidth per
non-virtual machine is 1 Gbps.

#### 3.4.3 Network Storage

The FCS network storage must meet the performance levels defined in
Table 3-6, which apply to persistent network storage attached by default
(referred to as Bundled Storage) to virtual machines and non-virtual
machines or as separately orderable block storage as identified in the
CCSD Section 6.2. These standards apply to each volume of block storage
ordered and attached to an instance regardless of the volume size. IOPS
performance is measured as asynchronous random reads using 4KB block
sizes and an IO depth of 4. Throughput performance is measured using
64KB block sizes. Storage Performance Level\_1 is only required for the
Private physical computing environment.

Table ‑ Network Storage Performance Level

  **Storage Performance Level**   **Throughput (MB/s)**   **IOPS**
  ------------------------------- ----------------------- ----------
  **1**                           **32**                  **4000**
  **2**                           **4**                   **500**
  **3**                           **0.8**                 **100**

### 3.5 Colocation Reliability, Maintainability, and Availability

The FCS colocation services must meet the reliability, maintainability,
and availability as defined by the Uptime Institute Tier III facility
standards with the resulting end-user availability based on site-caused
downtime of at least 99.98%. The data center facility must be provided
in a Tier III “self” certified facility. See Appendix A for a subset of
the Uptime Institute Tier III facility standards.

## 4. Operating Domains

### 4.1 Operating Domains Description
The FCS must provide distinct physical computing environments and
operating domains in which tenant applications are instantiated and run.
The operating domains are defined by the cloud computing deployment
model and functional role within the FAA organization, the types of data
flow, the software development life-cycle phase of tenant applications
which, in turn, influences the security, separation of duties, and other
traffic segregation requirements. The physical computing environments
and operating domains are defined in this Table 4-1 and graphically in
Figure 4-1.

Table 4-1 ‑ Operating Domains

|------------------------------------- +------------------------------------------------------------------------|
|  **Physical Computing Environment**  |  **Operating Domain**                                                  |
|:------------------------------------:|:----------------------------------------------------------------------:|
|   NAS Private Cloud                  | NAS Private Operational Domain                                         |
|                                      | NAS Private Operational Test Domain                                    |
|  Admin/Mission Support Private Cloud | Admin/Mission Support Private Operational Domain                       |
|                                      | Admin/Mission Support Private Operational Test Domain                  |
|  Government Community Cloud          | NAS Government Community Development/Test Domain                       |
|                                      | Admin/Mission Support Government Community Operational Domain          |
|                                      | Admin/Mission Support Government Community Operational Test Domain     |
|                                      | Admin/Mission Support Government Community Development/Test Domain     |
|  Public Cloud                        | Public Web Services Operational Domain                                 |
|  Admin/Mission Support Colocation    | Admin/Mission Support Colocation Operational Domain                    |
|  NAS Colocation                      | NAS Colocation Operational Domain                                      |
|:------------------------------------:|:----------------------------------------------------------------------:|

![](media/image3.emf){width="6.495833333333334in"
height="4.288194444444445in"}

Figure 4-1 Physical Computing Environments and Operating Domains

The following subsections define each of these operating domains in
th**e** context of their tenant applications and their roles in the FAA
operating domains.

#### 4.1.1 Operational Domains

The Operational Domains host tenant applications that are in the
operational phase of their life-cycle.

The NAS Private Operational Domain hosts tenant applications that are
part of NAS operational systems. The associated systems indirectly
support the FAA Air Traffic Organization real-time operation of the NAS.
Tenant applications in the NAS Operational domains are subject to formal
NAS configuration control and security controls. Tenant applications in
NAS Operational Domains may communicate directly with other NAS
operational systems – including systems hosted within the FCS and
systems external to the FCS via the Government-furnished Wide Area
Network (WAN) connections.

The Admin/Mission Support Private Operational and Admin/Mission Support
Government Community Cloud Operational Domains host tenant applications
that are part of FAA Administrative and Mission Support systems. Tenant
applications in the Admin/Mission Support Private Operational Domain may
communicate directly with other Admin/Mission Support Operational
systems – including systems hosted within the FCS and systems external
to the FCS via the Government-furnished WAN connections.

Tenant applications in both the NAS and Admin/Mission Support
Operational Domains do not communicate directly through the CSP network
with systems and tenant applications in other operating domains.

#### 4.1.2 Operational Test Domains

The Operational Test Domains host tenant applications that are
undergoing the formal operational testing phase of their life-cycle.
Formal operational testing is conducted to support the initial
In-Service Decision (ISD) for the associated system and when substantive
changes are being made to a system that is currently in the Operational
Domain. Upon successful completion of testing, tenant applications in
the Operational Test Domain will generally be instantiated into the
Operational Domain. Tenant applications in the Operational Test Domain
are subject to the formal configuration management practices defined for
the associated environment.

The Operational Test Domain is an extension of the existing FAA test
environment. Tenant applications in the FCS Operational Test Domains may
communicate with other systems within FAA test environments such as
those at the William J. Hughes Technical Center and the Mike Monroney
Aeronautical Center via the Government-furnished WAN connections.

Tenant applications in the NAS and Admin/Mission Support Operational
Test Domains do not communicate directly through the CSP network with
systems and tenant applications in other operating domains.

#### 4.1.3 Development/Test Domains

The Development/Test Domains host tenant applications that are under
development and are undergoing developer-level testing prior to being
handed-off to formal Operational testing conducted by the Government.
Tenant application developers are responsible for the configuration
management of their tenant applications.

Tenant applications in the NAS and Admin/Mission Support
Development/Test Domain may communicate with other systems within FAA’s
Research and Development (R&D) enclave via the Government-furnished WAN
connections. Systems in the FAA R&D enclave have no direct connectivity
to the FCS Operational Domain.

#### 4.1.4 Web Services Domain

The Web Services Domain hosts tenant applications that provide
information services accessible via the public Internet. Tenant
applications in the Web Services Domain do not communicate directly with
systems in the other operating domains. The Government-furnished WAN
connections will provide the network connectivity to tenant applications
hosted within the FAA’s internal network or the Internet.

#### 4.1.5 Colocation Operational Domains

Colocation Operational Domains host Government-furnished computing
infrastructure. Tenant applications in the Colocation Operational
Domains do not communicate directly with systems in the other operating
domains. Tenant applications in a Colocation Operational Domain must be
accessible via the Government-furnished WAN connections.

### 4.2 Physical Computing Environment and Operating Domain Security
The FCS must ensure the operational security of tenant applications
within each physical computing environment and operating domain. The FCS
operating domains must be implemented and operated in accordance with
the associated security requirements in the following subsections. All
physical computing environments and the cloud computing services
supporting the required operating domains must be FedRAMP compliant
(does not apply to Colocation). The Colocation and NAS Private Cloud
operating domains must also meet the FAA-specific supplemental controls
as defined in Attachment J-9. Access to the Contractor’s FedRAMP
documents and supporting materials must be made available to the FAA to
assess the risk and determine the final recommendation for an FAA agency
Authorization to Operate (ATO) for the individual physical computing
environments.

Access to the FCS cloud computing services must be controlled via a
Government-approved credential and authentication management system. The
system must support user and role provisioning and deprovisioning, and
support Security Assertion Markup Language (SAML) based authentication.
The system must be interoperable with the FAA’s credential and
authentication management systems that use centralized authority for
user-to-system and machine-to-machine authentication.

The FCS must prohibit non-FAA tenant applications message traffic from
crossing into the FAA operating domains.

Each FCS physical computing environment and remote operations control
center must support external network connections via the
Government-furnished WAN connections. The Government will provide all
telecommunications, IP addressing and standards, and policy governing IP
addressing for systems hosted in the FCS.

The FCS data centers must have a Statement of Standards for Attestation
Engagements (SSAE) No. 16 (formerly SAS-70) compliant data center
hosting the physical computing environments. The FCS Contractor must
provide SSAE-16 report documentation (most recent assessment and
remediation plans).

### 4.2.1 NAS Private Operational & Operational Test Domain Security
The NAS Private Operational and Operational Test Domains must be hosted
within a Private cloud and must be FedRAMP compliant at a level of FISMA
Moderate and implemented with FAA-specific supplemental controls as
defined in Attachment J-9.

The NAS Private physical computing environment must have physical
separation from these environments: Admin/Mission Support Private Cloud,
Government Community Cloud, the Public Web Services, Colocation, and any
non-FCS customers residing within the FCS Contractor’s data center
infrastructure. The NAS Private physical computing environment must be
provided within a secure and lockable cage. The NAS Private Operational
Domain must have logical separation from the NAS Private Operational
Test Domain.

#### 4.2.2 Admin/Mission Support Private Operational & Operational Test Domain Security

The Admin/Mission Support Private Operational and Operational Test
Domains must be hosted within a Private cloud and must be FedRAMP
compliant at a level of FISMA Moderate.

The Admin/Mission Support Private physical computing environment must
have physical separation from these environments: NAS Private Cloud,
Government Community Cloud, Public Web Services, Colocation, and any
non-FCS customers residing with the Contractor’s data center
infrastructure. The Admin/Mission Support Private physical computing
environment must be provided within a secure and lockable cage. The
Admin/Mission Support Operational Domain must have logical separation
from the Admin/Mission Support Operational Test Domain.

#### 4.2.3 Government Community Cloud Domain Security

The Government Community Cloud Domains may be hosted within a government
community cloud and must be FedRAMP compliant at a level of FISMA
Moderate. A government community cloud is a multi-tenant shared
computing infrastructure that is dedicated for government agencies
usage.

At a minimum, the Government Community Cloud physical computing
environment must have logical separation from the Public Cloud physical
computing environment and any other computing infrastructures.  The FCS
operating domains within the Government Community Cloud (i.e., NAS
Development/Test, Admin/Mission Support Operational, Admin/Mission
Support Operational Test, and Admin/Mission Support Development/Test)
must have logical separation from each other and any non-FCS customers
residing within the Contractor’s Government Community Cloud physical
computing environment.

#### 4.2.4 Public Web Services Domain Security

The Public Web Services Domain may be hosted within a public cloud and
must be FedRAMP compliant at a level of FISMA Moderate. A public cloud
is a multi-tenant shared computing infrastructure that is made available
to the general public or a large industry group.

At a minimum, the Public Cloud physical computing environment must have
logical separation from the Government Community Cloud physical
computing environment and any other computing infrastructures.  The FCS
Public Web Services operating domain must have logical separation from
any non-FCS customers residing within the Contractor’s Public Cloud
physical computing environment.

#### 4.2.5 Colocation Operational Domain Security

The Colocation Operational Domain must be hosted within a Tier III
“self”-certified data center facility and provided within a secure and
lockable cage.

The dedicated physical network cable connecting the Local Area Network
(LAN) of the Government-furnished IT network equipment within the
colocation space to the Government-furnished WAN connections must be
physically secured and must not be used for other LAN connectivity
within the Contractor facility including LAN connections to other
domains.

The space provided under the Colocation Operational Domain must be
controlled and secured from unauthorized access.

-   The FCS Colocation Space must include a locked cage and locked
    server cabinets/racks to host FAA IT assets.

-   The data center facility providing the FCS Colocation Space must
    include the following physical security protections at a minimum:

    -   a security wall or fencing enclosing the perimeter of data
        center property,

    -   a security gate for controlling access to the facility,

    -   surveillance cameras,

    -   security guard personnel to monitor the physical security and
        verify the access credentials of personnel entering the
        facility, and

    -   electronic or physical locks to caged spaces.

##### 4.2.5.1 NAS Colocation Operational Domain Security
The NAS Colocation Operational Domain must implement the NIST 800-53
infrastructure controls and FAA-specific supplemental infrastructure
controls defined in Attachment J-9.

The NAS Colocation physical computing environment must have physical
separation from these environments: Admin/Mission Support Colocation,
the NAS Private Cloud, the Admin/Mission Support Private Cloud, the
Government Community Cloud, the Public Web Services, and any non-FCS
customers residing within the Contractor’s data center infrastructure.
The NAS Colocation physical computing environment must be provided
within a secure and lockable cage.

##### 4.2.5.2 Admin/Mission Support Colocation Operational Domain Security
The Admin/Mission Support Colocation Operational Domain must implement
the NIST 800-53 infrastructure controls.

The Admin/Mission Support Colocation physical computing environment must
have physical separation from these environments: NAS Colocation, the
NAS Private Cloud, the Admin/Mission Support Private Cloud, the
Government Community Cloud, the Public Web Services, and any non-FCS
customers residing within the Contractor’s data center infrastructure.
The Admin/Mission Support Colocation physical computing environment must
be provided within a secure and lockable cage.

### 4.3 Tenant Application and Data Security
The FCS must prohibit any tenant application from disrupting the operation of another tenant application in the same operating domain or a different operating domain.

The FCS must prohibit any tenant application from accessing data in the
memory and storage of another FCS tenant application in the same
operating domain or different operating domain.

The FCS must employ cryptographic mechanisms to protect the
confidentiality and integrity of Government information, including both
Government data-at-rest and Government data-in-transit. Encrypted
Government information must be encrypted using NIST-validated and
Federal Information Processing Standard (FIPS) 140-2 compliant/validated
cryptographic modules in accordance with DOT Order 1351.37 and FAA Order
1370.103.  

### 4.4 Cloud Management Tool Security Requirements for Monitoring and Control
The monitoring and control capabilities for the NAS Private Cloud must
be physically separate from the monitoring and control capabilities of
other FCS physical computing environments. Control of cloud
infrastucture may not be shared across multiple physical computing
environments.  Monitoring of cloud infrastructure may be shared across
physical computing environments with the exception of the NAS Private
Cloud.

## 5. Network Interface and Inter-process Communication Requirements

### 5.1 Local Area Network Connectivity
The FCS must provide LAN connectivity between:
1. the service delivery points for the Government-furnished WAN connections and the FCS physical computing environments hosting tenant applications (except for colocation spaces since the FAA will be providing LAN connectivity for Government-furnished
computing infrastructure)
2. the FCS operating domains hosting tenant applications;
3. tenant applications running on different operating domains within the same physical computing environment;
4. the FCS networked storage.

The FCS LAN connectivity must be interoperable with the Government-furnished WAN connections defined in CCSD Section 5.2.

The FCS LAN connectivity must meet the separation requirements defined in CCSD 4.0.

### 5.2 Government-furnished Wide Area Network Connections
The FCS physical computing environments must comply with the telecommunications service interface specifications defined in Attachment J-2 User Guide for Government-furnished WAN services.

The FCS must provide power, space and cooling of colocation space to host the Government-furnished WAN equipment as defined in the PWS paragraph C.3.1.

For the FCS physical computing environments or data center facilities
providing colocation, cloud computing services and remote operations
control centers, any inter-facility connections must be via the
Government-furnished WAN connections as described in PWS C.3.0.
Inter-facility connections are defined as connections that traverse
telecommunications carrier infrastructure.

### 5.3 Internet Connectivity
Any connections from the FCS physical computing environment to the
public Internet must be via the following WAN connection options:
1. DOT Trusted Internet Connection Access Providers (TICAPs), or
2. DOT-approved Managed TIC Provider Services (MTIPSs).

### 5.4 Inter-process Communications
The FCS must support inter-process communications between tenant
applications within the same operating domain whether they are running
on the same physical virtual host/clusters, virtual infrastructure, or
different physical or virtual infrastructure. The FCS must support
inter-process communications in accordance with the performance levels
specified in CCSD Section 3.4.3 and the service class definition.

### 5.5 Application Programming Interface
The FCS must provide an Application Programming Interface (API) to allow
tenant applications to request data, change attributes, and manage the
computing resources such as elastically obtaining more computing
resources. The API must allow tenant applications in a load balanced and
scalable environment, to provision and deprovision additional virtual
machine instances and/or RAM (1 GB increment) past the committed
resources allocated to the base-level ordered as defined in section 7.5.

The API must provide the ability to protect the existing storage volume
data, and format and extend the existing storage volume. The API must
provide the ability to add a new volume to the existing VM or Non-VM.

The API must be development platforms independent.

The FCS must prohibit tenant applications from using the API to
provision unordered elastic virtual machine instance and/or RAM.

The FCS must prohibit tenant applications from using the API to
provision elastic virtual machine instance and/or RAM beyond the
allocated threshold or ordered limits.

### 5.6 Virtualization Platform
The FAA is currently standardized on the VMWare virtualization platform.
The FAA is open to other solutions that the Contractor may provide.

### 5.7 IPv6
The FCS must support the IPv4 and IPv6 protocols.

## 6. Service Class Descriptions
The following subsections describe the required service classes that
must be available for order and implementation within the relevant FCS
operating domains.

### 6.1 Computing Services
The FCS must provide computing services as defined in the following subsections for all operating domains defined in CCSD Section 4 except for the Colocation Operating Domain.

#### 6.1.1 Virtualized Machines
The FCS must provide persistent Virtualized Machine (VM) for the
instantiation of tenant application images into the operating domains in
accordance with the ordered service class. The VM service classes are
defined in terms of the number of cores, the amount of RAM, the amount
of Bundled Storage, and the Network I/O bandwidth. In all cases, the
default storage performance level for Bundled Storage is level 3. The
default Network I/O is 100 Mbps.

The FCS must support upgrading the default storage performance level 3
to level 2 or 1 via the online Account Management User Interface.

The FCS must support the creation of persistent VMs without the
operating system by default. The operating system will be provided by
the Government as part of the tenant application image. In the case
where the VM includes the operating system as ordered, the Government
will identify the specific version of the operating system by ordering
the supplemental feature described in Section 7.4.

The FCS must support the creation of a VM “snapshot” for all service
classes listed in Table 6‑1 to be stored in the bundled storage or
supplemental storage volume. The VM snapshot must preserve the state and
data of a VM at a point in time. The FCS VM snapshot function must be
provided via an API and the on-line FCS account management user
interface to allow the tenant application to invoke multiple snapshots,
delete snapshots, and restore a snapshot as the active virtual machine.

Table 6‑1 identifies the required service classes for VMs without the
operating system that must be available through the FCS as ordered.
Other service classes may be added as needed. For a VM provided without
an operating system, the Government supplies the operating system.
Service classes are also provided for additional cores, RAM, and bundled
storage.

_Table 6‑1 Service Classes for Virtualized Machines without an Operating System_

|------------------------+---------------+-----------+--------------+--------------------------+------------------------|
| **Service Class Code** | **RMA Level** | **Cores** | **RAM (GB)** | **Bundled Storage (GB)** | **Network I/O (Mbps)** |
|:-----------------------|:--------------|:----------|:-------------|:-------------------------|:-----------------------|
| VM1A                   | Level\_1      | 1         |  2           |   75                     |    100                 |
| VM1B                   | Level\_2      | 1         |  2           |   75                     |    100                 |
| VM1C                   | Level\_3      | 1         |  2           |   75                     |    100                 |
| VM2A                   | Level\_1      | 2         |  4           |   75                     |    100                 |
| VM2B                   | Level\_2      | 2         |  4           |   75                     |    100                 |
| VM2C                   | Level\_3      | 2         |  4           |   75                     |    100                 |
| VM3A                   | Level\_1      | 4         |  8           |   75                     |    100                 |
| VM3B                   | Level\_2      | 4         |  8           |   75                     |    100                 |
| VM3C                   | Level\_3      | 4         |  8           |   75                     |    100                 |
| VM4A                   | Level\_1      | 8         |  16          |   75                     |    100                 |
| VM4B                   | Level\_2      | 8         |  16          |   75                     |    100                 |
| VM4C                   | Level\_3      | 8         |  16          |   75                     |    100                 |
| VM5A                   | Level\_1      | 16        |  32          |   75                     |    100                 |
| VM5B                   | Level\_2      | 16        |  32          |   75                     |    100                 |
| VM5C                   | Level\_3      | 16        |  32          |   75                     |    100                 |
| VM\_VPUA\_ADD          | Level\_1      | 1         |              |                          |                        |
| VM\_RAMA\_ADD          | Level\_1      |           |   1          |                          |                        |
| VM\_STOA\_ADD          | Level\_1      |           |              |    1                     |                        |
| VM\_VPUB\_ADD          | Level\_2      | 1         |              |                          |                        |
| VM\_RAMB\_ADD          | Level\_2      |           |   1          |                          |                        |
| VM\_STOB\_ADD          | Level\_2      |           |              |    1                     |                        |
| VM\_VPUC\_ADD          | Level\_3      | 1         |              |                          |                        |
| VM\_RAMC\_ADD          | Level\_3      |           |   1          |                          |                        |
| VM\_STOC\_ADD          | Level\_3      |           |              |    1                     |                        |
|------------------------+---------------+-----------+--------------+--------------------------+------------------------|

The computing service class codes in Table 6‑1 are appended by “\_PVT\_N” in Section B Table B.3.1 for a private VM in the NAS Private Domain.

The computing service class codes in Table 6‑1 are appended by “\_PVT\_M” in Section B Table B.3.2 for a private VM in the Admin/Mission Support Private Domain.

The computing service class codes in Table 6‑1 are appended by “\_COM” in Section B Table B.3.3 for a community VM in the Government Community Cloud Domain.

The computing service class codes in Table 6‑1 are appended by “\_PUB” in Section B Table B.3.4 for a public VM in the Public Web Services Domain.

#### 6.1.2 On-demand Virtualized Machines

The FCS must provide on-demand virtualized computing services with the same characteristics and service classes as described in Section 6.1.1. On-demand virtual machines may be ordered directly or may be
instantiated by utilizing the elasticity supplemental feature described in Section 7.5. When instatiated through the elasticity feature, the API described in CCSD Section 5.5 must provide tenant applications with the
ability to manage the number of on-demand virtualized computing service instances and their state.

Use of the on-demand virtualized computing service is defined in terms of “instance hours.” For example, two (2) instances of an 8-core VM allocated for two hours would equate to four (4) “instance hours.”

The computing service class numbers in Table 6‑1 are appended by “\_PVT\_N” and prepended by “OD\_” in Section B Table B.3.5 for a Private on-demand VM in the NAS Private Domain.

The computing service class numbers in Table 6‑1 are appended by “\_PVT\_M” and prepended by “OD\_” in Section B Table B.3.6 for a Private on-demand VM in the Admin/Mission Support Private Domain.

The computing service class numbers in Table 6‑1 are appended by “\_COM”
and prepended by “OD\_” in Section B Table B.3.7 for a Community
on-demand VM in the Government Community Cloud Domain.

The computing service class numbers in Table 6‑1 are appended by “\_PUB”
and prepended by “OD\_” in Section B Table B.3.8 for a Web Services
Public on-demand VM in the Public Web Services Domain.

The requirements for when the on-demand virtualized computing service
must be made available, when the additional resources must be
de-allocated, limitations on its use, and the ordering construct are
defined in Section C.4.5.2.

An on-demand virtualized computing service must support three different
states:

1.  Shutdown: The VM image is available via ordered networked storage. The on-demand virtualized computing service does not consume any ordered instance hours.
2.  Running: One or more instances of the VM image are running in a corresponding compute service class. The on-demand virtualized computing service consumes ordered instance hours for each VM instance.
3.  Discontinued: The on-demand virtualized computing service was shut down and the corresponding VM image on the networked storage was deleted.

#### 6.1.3 Non-Virtualized Machines
The FCS must provide Non-Virtualized Machines (NVMs) service classes
that correspond to a specific allocation of physical computing resources
for hosting tenant applications. NVMs are not required in the Public
Cloud physical computing environment. The NVM service classes are
defined in terms of the number of cores, the amount of RAM, the amount
of Bundled Storage, and the Network I/O bandwidth. In all cases, the
default performance level for Bundled Storage is Level\_3 based upon the
file operating system in use. The FCS must support the allocation of
NVMs with and without the operating system. In the case where the NVM
service class does not include the operating system, it will be provided
by the Government as part of the tenant application image. In the case
where the NVM service class includes the operating system, the
Government will identify the specific version of the operating system by
ordering it as a supplemental feature as defined in CCSD Section 7.4.
Service classes are also provided for additional RAM and bundled
storage.

Table 6‑2 identifies the required service classes for NVMs that must be
available through the FCS as ordered in any operating domain. The
service classes in Table 6‑2 correspond to the NVM service classes in
Section B Tables B.3.9 through B.3.11. Other service classes may be
added as needed. For a NVM provided without an operating system, the
Government will supply the operating system.

_Table 6‑2 Service Classes for Non-Virtualized Machine without an Operating System_

|---------------------------+---------------+-----------+---------------+---------------------------+---------------------------|
|  **Service Class Code**   | **RMA Level** | **Cores** | **RAM (GB)**  | **Bundled Storage (GB)**  | **Network I/O (Gbps)**    |
|:--------------------------|:--------------|:----------|:--------------|:--------------------------|:--------------------------|
|  NVM1A                    |   Level\_1    |    4      |     8         |     75                    |     1                     |
|  NVM1B                    |   Level\_2    |    4      |     8         |     75                    |     1                     |
|  NVM1C                    |   Level\_3    |    4      |     8         |     75                    |     1                     |
|  NVM2A                    |   Level\_1    |    8      |     16        |     75                    |     1                     |
|  NVM2B                    |   Level\_2    |    8      |     16        |     75                    |     1                     |
|  NVM2C                    |   Level\_3    |    8      |     16        |     75                    |     1                     |
|  NVM3A                    |   Level\_1    |    16     |     32        |     75                    |     1                     |
|  NVM3B                    |   Level\_2    |    16     |     32        |     75                    |     1                     |
|  NVM3C                    |   Level\_3    |    16     |     32        |     75                    |     1                     |
|  NVM4A                    |   Level\_1    |    32     |     64        |     75                    |     1                     |
|  NVM4B                    |   Level\_2    |    32     |     64        |     75                    |     1                     |
|  NVM4C                    |   Level\_3    |    32     |     64        |     75                    |     1                     |
|  NVM5A                    |   Level\_1    |    64     |     128       |     75                    |     1                     |
|  NVM5B                    |   Level\_2    |    64     |     128       |     75                    |     1                     |
|  NVM5C                    |   Level\_3    |    64     |     128       |     75                    |     1                     |
|  NVM\_RAMA\_ADD           |   Level\_1    |           |     1         |                           |                           |
|  NVM\_STOA\_ADD           |   Level\_1    |           |               |     1                     |                           |
|  NVM\_RAMB\_ADD           |   Level\_2    |           |     1         |                           |                           |
|  NVM\_STOB\_ADD           |   Level\_2    |           |               |     1                     |                           |
|  NVM\_RAMC\_ADD           |   Level\_3    |           |     1         |                           |                           |
|  NVM\_STOC\_ADD           |   Level\_3    |           |               |     1                     |                           |
|---------------------------+---------------+-----------+---------------+---------------------------+---------------------------|

The computing service class numbers in Table 6-2 are appended by
“\_PVT\_N” in Section B Table B.3.9 for a private NVM in the NAS Private
Domain.

The computing service class numbers in Table 6-2 are appended by
“\_PVT\_M” in Section B Table B.3.10 for a private NVM in the
Admin/Mission Support Private Domain.

The computing service class numbers in Table 6‑12 are appended by
“\_COM” in Section B Table B.3.11 for a community NVM in the Government
Community Cloud Domain.

### 6.2 Persistent Storage
The FCS must provide persistent network storage. The FCS must provide
three forms of persistent network storage: (1) on-line network storage
that is available and accessible by cloud-based tenant applications
during run-time; and (2) archived storage that is maintained off-line,
but is available to be loaded into network storage as defined in PWS
paragraph C.4.5.2; and (3) on-line remote storage that is available for
non-cloud tenant applications. The following subsections identify the
requirements specific to the three types of persistent storage.

The FCS storage device per physical computing environment must be
physically separated, but at a minimum the remote storage devices must
be logically separated for Government Community and Public Cloud
physical computing environments. The FCS storage device can be shared,
but logically separated across the operating domains within that
physical computing environment.

#### 6.2.1 On-line Network Storage

The FCS must provide on-line network storage for use by tenant
applications. The FCS on-line network storage must support the storage
system standards as required by tenant applications’ operating systems.

The FCS must provide on-line network storage to meet or exceed the range
of performance levels defined in CCSD Section 3.4.4.

The FCS must limit read/write access to on-line network storage to the
associated tenant application. Increases to the amount of the on-line
network storage allocated to a tenant application must not affect
storage or availability of existing data.

Data stored in the FCS on-line network storage must remain available
until over-written by the tenant application or until the tenant
application discontinues the associated FCS computing service.

Decreases (e.g. discontinued storage service or a decrease in the size
of the ordered volume) to the amount of the FCS on-line network storage
allocated to a tenant application must not affect the storage or
availability of the existing data in the FCS on-line network storage
provided that amount of data stored by the tenant fits within the
reduced allocation.

Performance Level\_1 for the FCS on-line network storage is only
required for VMs in the Private Cloud operating domains and for NVMs in
all operating domains.

The FCS must provide tenant applications with the ability to move data
residing on one on-line network storage performance level to a different
storage performance level.

Table 6-2-1 identifies the feature codes for the FCS on-line networked
storage based on the storage performance levels defined in CCSD Section
3.4.4 and the service availability (RMA Level) as described as defined
in CCSD Section 3.2.

The storage service class codes in Table 6‑1 are appended by “\_PVT\_N”
in Section B Table B.3.13 for private storage in the NAS Private Domain.

The storage service class codes in Table 6‑1 are appended by “\_PVT\_M”
in Section B Table B.3.14 for private storage in the Admin/Mission
Support Private Domain.

The storage service class codes in Table 6‑1 are appended by “\_COM” in
Section B Table B.3.15 for community storage in the Government Community
Cloud Domain.

The storage service class codes in Table 6‑1 are appended by “\_PUB” in
Section B Table B.3.16 for public storage in the Public Web Services
Domain.

_Table 6-2-1 Feature Codes for On-line Networked Storage_

|---------------------------+-------------------------------+-------------------|
|  **Service Class Code**   | **Storage Performance Level** | **RMA Level**     |
|:--------------------------|:------------------------------|:------------------|
|  SS\_1A                   |   1                           |    Level\_1       |
|  SS\_2A                   |   2                           |    Level\_1       |
|  SS\_3A                   |   3                           |    Level\_1       |
|  SS\_1B                   |   1                           |    Level\_2       |
|  SS\_2B                   |   2                           |    Level\_2       |
|  SS\_3B                   |   3                           |    Level\_2       |
|  SS\_1C                   |   1                           |    Level\_3       |
|  SS\_2C                   |   2                           |    Level\_3       |
|  SS\_3C                   |   3                           |    Level\_3       |
|---------------------------+-------------------------------+-------------------|


#### 6.2.2 Archived Off-line Storage

The FCS must provide archived storage for use by tenant applications.
The FCS must support the transfer of data in archived storage to on-line
networked storage. The FCS must limit access to archived storage to the
associated tenant application. At the request of the tenant, the
contractor is responsible for mounting or reloading data from the
archive storage to the on-line networked storage within 48 hours. 

Data stored in the FCS archive storage, including data copied into
on-line networked storage, must remain available in archived storage
until the tenant application discontinues the associated FCS computing
service. Upon discontinuation of the associated computing services, data
in archived storage must remain available for two weeks, per the
conditions defined in Section H.7.

Increases to the amount of the FCS archived storage allocated to a
tenant application must not affect the storage or availability of the
existing data in the FCS archived storage.

Decreases to the amount of the FCS archived storage allocated to a
tenant application must not affect the storage or availability of the
existing data in the FCS archived storage provided that amount of data
stored by the tenant fits within the reduced allocation.

The SS\_ARCH\_XXX feature codes associated with the FCS archived storage
are identified in Section B Tables B.3.13, B.3.14, B.3.15, and B.3.16.

#### 6.2.3 Remote Storage Service

The FCS must provide Remote Storage service for non-Cloud tenant
applications as described in the CCSD Section 3.4.4. In all cases, the
default performance level for Remote Storage service must be Level\_3.
The Remote Storage service requires storage performance Level\_3 and the
following:

-   Real-Time access to the data store; and

-   Accessibility via a Contractor provided secure remote storage
    management agent or via a web browser through a secure
    transport mechanisms.

Table 6-2-3 identifies the required remote storage service classes that
must be provided through the FCS as ordered.

_Table 6-2-3 Feature Code for Remote Storage Service_

|---------------------------+---------------------------+-------------------|
| **Service Class Code**    | **Storage Performance Level**      |  **RMA Level**    |
|:--------------------------|:--------------------------|:------------------|
|  RS\_3A                   |   3                       |  Level\_1         |
|  RS\_3B                   |   3                       |  Level\_2         |
|  RS\_3C                   |   3                       |  Level\_3         |
|---------------------------+---------------------------+-------------------|

### 6.3 Colocation Services

Table 6‑3 identifies the Colocation service classes that correspond to
the basic order commodity for computing facility space where
Government-owned equipment will be located and operated.

The colocation facility/space must include power to operate the
equipment and it must be environmentally controlled within the operating
specifications of the equipment and to the Tier III “self”-certified
facility requirements. FCS must regularly maintain the temperature and
humidity within the colocation facility in accordance with the 2011
ASHRAE Thermal Guidelines for a Class A1 data center. Colocation space
ordered in quantities greater than one must be contiguous. All
colocation space ordered within the projected annual service plan must
be contiguous. FCS must provide a work area (with at least 2tables/desks
and 2 chairs) of at least 100 sq. ft. adjacent to the caged colocation
space for government personnel usage.

Colocation must be provided in at least two (2) Contractor-provided data
center facilities. 

_Table 6‑3 Service Classes for Colocation Services_

  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
  Service Class Code   Description                                  Unit                 Performance
  -------------------- -------------------------------------------- -------------------- ------------------------------------------------------------------------------------------------------------------------------------
  Colo\_Svc\_1         Caged and Locked Colocation Space            25 square feet       Data center must conform to Tier III “self” certified facility

  Colo\_Svc\_2         Powered Standard Rack and lockable Cabinet   42U                  -   Rack must measure:

                                                                                             -   600 mm wide

                                                                                             -   1070 mm deep

                                                                                         -   Rack must conform to EIA-310 standard



  Colo\_Svc\_3         Powered Wide Rack and lockable Cabinet       42U                  -   Rack must measure:

                                                                                             -   750 mm wide

                                                                                             -   1070 mm deep

                                                                                         -   Rack must conform to EIA-310 standard



  Colo\_Svc\_4         Powered Deep Rack and lockable Cabinet       42U                  -   Rack must measure:

                                                                                             -   600 mm wide

                                                                                             -   1200 mm deep

                                                                                         -   Rack must conform to EIA-310 standard



  Colo\_Svc\_5         Rack power                                   1 KWh                Power must conform to Tier III “self” certified facility requirements. The average physical server power consumption is 400 watts.

  Colo\_Svc\_6         Network connectivity per foot                10 Giga Bit/second   Per IEEE 802.3
  ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Table 6‑4 identifies the Power Distribution Unit Types that must be
orderable for Colo\_Svc\_2, Colo\_Svc\_3, Colo\_Svc\_4, and
Colo\_Svc\_5.

_Table 6‑4 Power Distribution Unit Types_

  **Service Class Code**   **Description**                                **Receptacle Type**   **Phase**   **Output Voltage**   **Input Voltage**   **Amperage**   **Electrical Plug**   **U Space**
  ------------------------ ---------------------------------------------- --------------------- ----------- -------------------- ------------------- -------------- --------------------- ----------------
  PDU\_A\_1                Basic Power Distribution Unit                  IEC 320 C13           1           208                  208                 30             L6-30P                Zero U
  PDU\_B\_1                Metered Power Distribution Unit                IEC 320 C13           1           208                  208                 30             L6-30P                Zero U
  PDU\_C\_1                Switched and Metered Power Distribution Unit   IEC 320 C13           1           208                  208                 30             L6-30P                Zero U
  PDU\_A\_2                Basic Power Distribution Unit                  IEC 320 C13           3           208                  208 3P              50             CS8365C               Zero U
  PDU\_B\_2                Metered Power Distribution Unit                IEC 320 C13           3           208                  208 3P              50             CS8365C               Zero U
  PDU\_C\_2                Switched and Metered Power Distribution Unit   IEC 320 C13           3           208                  208 3P              50             CS8365C               Zero U
  PDU\_A\_3                Basic Power Distribution Unit                  IEC 320 C19           1           208                  208                 30             L6-30P                Zero U
  PDU\_B\_3                Metered Power Distribution Unit                IEC 320 C19           1           208                  208                 30             L6-30P                Zero U
  PDU\_C\_3                Switched and Metered Power Distribution Unit   IEC 320 C19           1           208                  208                 30             L6-30P                Zero U
  PDU\_A\_4                Basic Power Distribution Unit                  IEC 320 C19           3           208                  208 3P              50             CS8365C               Zero U
  PDU\_B\_4                Metered Power Distribution Unit                IEC 320 C19           3           208                  208 3P              50             CS8365C               Zero U
  PDU\_C\_4                Switched and Metered Power Distribution Unit   IEC 320 C19           3           208                  208 3P              50             CS8365C               Zero U
  PDU\_A\_5                Basic Power Distribution Unit                  NEMA 5-15             1           110/115              120                 15             NEMA 5-15P            Rack Mountable
  PDU\_B\_5                Metered Power Distribution Unit                NEMA 5-15             1           110/115              120                 15             NEMA 5-15P            Rack Mountable
  PDU\_C\_5                Switched and Metered Power Distribution Unit   NEMA 5-15             1           110/115              120                 15             NEMA 5-15P            Rack Mountable
  PDU\_A\_6                Basic Power Distribution Unit                  NEMA 5-15             1           110/115              120                 15             NEMA 5-15P            Zero U
  PDU\_B\_6                Metered Power Distribution Unit                NEMA 5-15             1           110/115              120                 15             NEMA 5-15P            Zero U
  PDU\_C\_6                Switched and Metered Power Distribution Unit   NEMA 5-15             1           110/115              120                 15             NEMA 5-15P            Zero U

The colocation service class codes in Table 6-3 begin with “COLO\_N” in
Section B Table B.3.17 for colocation service in the NAS Colocation
Domain.

The colocation service class codes in Table 6‑1 begin with “COLO\_M” in
Section B Table B.3.18 for colocation service in the Admin/Mission
Support Colocation Domain.

The power distribution service class codes in Table 6-4 begin with
“PDU\_N” in Section B Table B.3.17 for power distribution service in the
NAS Colocation Domain.

The power distribution service class codes in Table 6-4 begin with
“PDU\_M” in Section B Table B.3.18 for power distribution service in the
Admin/Mission Support Colocation Domain.

### 6.4 Other Services

Some FAA tenant applications may require imagery data from National
Oceanic and Atmospheric Administration’s (NOAA) Geostationary
Operational Environmental Satellites (GOES). The imagery data required
by the NAS systems is made freely available via the “NOAAPORT” broadcast
system which is operated by NOAA. The NOAAPORT broadcast system provides
a one-way broadcast communication of NOAA environmental data and
information in near-real time to NOAA and external users. This broadcast
service is implemented by a commercial provider of satellite
communications utilizing C-band frequencies.

When ordered, the FCS must provide access to all the NOAAPORT data via a
local LAN to any service class in the NAS Colocation Space, NAS Private
Domain and the NAS Government Community Cloud Development/Test Domain.
The NOAAPORT equipment must be located at the data center facilities
hosting FCS tenants. NOAAPORT data must be available for each NAS
operating domain at the levels defined in Table 6‑5.

_Table 6‑5 NOAAPORT Service classes_

  Service Class Code   RMA Level
  -------------------- -----------
  NOAAPORT\_1          Level\_2
  NOAAPORT\_2          Level\_3

## 7. Supplemental Features

### 7.1 Monitoring as a Service (MaaS)

The FCS must provide Monitoring as a Service (MaaS) capability for
individual tenant applications as an optionally ordered feature. The FCS
MaaS capability must support the Simple Network Management Protocol
(SNMP) and other industry standards such as Windows Management
Instructions (WMI), and enable tenant applications to define and
implement Management Information Base (MIB) files for obtaining
real-time status information pertaining to the utilization of the FCS
services. The FCS MaaS capability must make all parameters listed in
CCSD Section 8.2 available to tenant applications for the operating
domains as a whole and for specific subsets of tenant applications.

The FCS MaaS capability must support the integration and execution of
tenant-developed agents,\
MIBs, and other interfaces within the FCS and must be documented in the
FCS Computing Services User’s Guide (CDRL F016). The FCS MaaS capability
must provide protections against “event storms” and similar occurrence
that could disrupt the execution of tenant applications.

The scope of a particular instantiation of the MaaS capability is
defined in terms of the number of different types of SNMP traps, the
number of SNMP traps per hour, the number of distinct business rules,
and the number of logical views that it is required to support.
*Business rules* initiate actions such as sending traps/notifications
and performing predefined operations when a given rule logic is
evaluated as true. Business rules correlate multiple alarm conditions to
a higher level notification (analogous to an “aggregate alarm”). A
*logical view* is a set of monitored attributes that are combined to
form a particular status display. Logical views provided through the
MaaS supplemental feature must be available through the Performance
Monitoring User Interface as defined in CCSD Section 9.2.

Table 7‑1 identifies feature codes for ordering MaaS capabilities in
terms of the ranges in the numbers of the various parameters.

Table 7‑1 MaaS Feature Levels [TO-BE-DETERMINED]

|-----------------------+-------------------------------+-----------------------------------+---------------------------------------+-------------------------------+
| **MaaS Feature Code** | **Number of SNMP Trap Types** | **Number of SNMP Traps per hour** | **Number of Distinct Business Rules** |  **Number of Logical Views**  |
|:----------------------|:------------------------------|:----------------------------------|:--------------------------------------|:------------------------------|
| MaaS1                 |                               |                                   |                                       |                               |
| MaaS2                 |                               |                                   |                                       |                               |
|-----------------------+-------------------------------+-----------------------------------+---------------------------------------+-------------------------------+

### 7.2 Network I/O Bandwidth

The FCS must provide additional network bandwidth as a supplemental
feature that is separately orderable in association with tenant
applications in increments of 100 Mbps for VMs. For NVMs, the FCS must
provide additional network bandwidth as a supplemental feature in
increments of 1 Gbps and has single or multiple port connections.

### 7.3 Reserved

### 7.4 Operating System for VMs and NVMs

The FCS must provide VMs and NVMs that include the operating system as a
supplemental feature specified by the Government as part of the service
order. The FCS must maintain and own these operating system licenses.

Table 7‑2 identifies the required operating systems that must be
available through the FCS as ordered. Other operating systems may be
added as needed. For a VM or NVM provided with an operating system, the
FCS must provide the bundled storage operating system and format as
appropriate to be used.

The feature codes in table 7-2 are appended by “\_PVT” in Section B
Table B.3.21 for private operating systems in the NAS Private and
Admin/Mission Support Private Domains.

The feature codes in Table 6‑1 are appended by “\_COM” in Section B
Table B.3.21 for community operating systems in the Government Community
Cloud Domain.

The feature codes in Table 6‑1 are appended by “\_PUB” in Section B
Table B.3.21 for public operating systems in the Public Web Services
Domain.

The feature codes in Table 6‑1 are appended by “\_NVM” in Section B
Table B.3.21 for Non-VMs in all domains.

Table 7‑2 Operating Systems

|  **Feature Code** |  **Description**                  | **OS**
|-------------------|---------------------------------  |---------
|  OS\_WIN\_1       | Windows Server® 2008 Standard     |  Windows
|  OS\_WIN\_2       | Windows Server® 2008 Enterprise   |  Windows
|  OS\_WIN\_3       | Windows Server® 2012              |  Windows
|  OS\_LINUX\_1     | Red Hat® Enterprise Linux® 5.5    |  Linux
|  OS\_LINUX\_2     | Red Hat® Enterprise Linux® 6      |  Linux

Elasticity

The FCS must provide the capability for elastic VM instances and elastic
RAM (1 GB increments) as distinct supplemental features that are
separately orderable.

The elasticity supplemental feature provides persistent virtual machines
with the capability of instantiating on-demand virtual machines (Section
6.1.2). The resource management (e.g. automated provisioning and
deprovisioning) associated with elastic resources will be performed by
tenant applications using the API defined in CCSD Section 5.5. Use of
the elastic virtual machine instance capability is defined in terms of
“instance hours.” For example, two (2) additional instances of an 8-core
VM allocated for two hours would equate to four (4) “instance hours.”
The elastic instance supplemental feature will be ordered for a VM using
the Supplemental Service Feature Code applicable to the operating
domain. Charging for the actual usage of the elastic VMs will utilize
the appropriate on-demand VM CLINs.

The FCS elastic RAM capability must enable tenant applications to exceed
the RAM allocated of their base-level service class instance through the
automatic allocation of additional RAM in increments of 1 GB.

Use of the elastic RAM capability is defined in terms of “instance
hours.” The elastic RAM supplemental feature will be ordered in
association with a VM using the Supplemental Service Feature Code
applicable to the operating domain.

Disaster Recovery

The FCS must support Disaster Recovery (DR) of computing and storage
services as a separately ordered supplemental feature for all physical
computing environments excluding colocation.  The FCS must support DR to
protect against prolonged loss of the physical computing environments or
the physical data center facility hosting the primary services (e.g.
active services that are providing computing resources to the tenant
application versus standby services at the DR site).  The FCS must be
capable of re-hosting or provisioning all services and the tenant
applications to the alternate data center facility within a defined
timeframe as defined in Table 7-3.  The maximum allowed data loss for
each service must be less than or equal to the recovery point objective.
The service restoral in the alternate data center must be less than or
equal to the recovery time objective.

The physical data center providing the DR services must be
geographically separated by a distance of no less than 500 miles from
the primary data center. The vendor must successfully conduct at least
one DR test per calendar year per tenant application procured DR
services.   The contingency and DR testing, inclusive of DR must be
conducted according to NIST 800-34, DOT Order 1351.37, and the FAA
Information Security Authorization Handbook. 

Table 7-3 Disaster Recovery Timeframes

  **Feature Code**   **Recovery Time Objective (RTO)**   **Recovery Point Objective (RPO)**
  ------------------ ----------------------------------- ------------------------------------
  DR\_TF1            20 minutes                          20 minutes
  DR\_TF2            8 hours                             4 hours
  DR\_TF3            5 days                              24 hours
  DR\_TF4            30 days                             1 week
  DR\_TF5            No DR required                      No DR required


----------------------------------------------------

## 8. Monitoring and Control Requirements

The FCS must implement a Monitoring and Control Function that supports
performance and security monitoring of the physical computing
environments across all operating domains and the service classes and
supplemental features in use by individual tenant applications.

The FCS must also support the monitoring of the service classes
supporting the tenant applications within each operating domain.
Monitoring information specific to tenant applications and operating
domains must be available on-line to authorized users as specified in
Section 9.2. Failure of the Monitoring and Control Function must not
cause an outage of any tenant application operating within the FCS.

### 8.1 Computing Infrastructure Monitoring and Control Capability

The computing infrastructure Monitoring and Control Capability must
detect any anomalous behavior including hardware and software component
failures, degraded performance, and any performance that does not meet
the FCS’s specifications and/or applicable Service Level Agreement (SLA)
provisions as defined in Attachment J-6.

The computing infrastructure Monitoring and Control Capability must
provide authorized FCS Government personnel with the ability to remotely
reconfigure and restart services that are within the Government’s
responsibility that may not be functioning properly.

The computing infrastructure Monitoring and Control Capability must
monitor and provide alarms on the following infrastructure parameters
for each operating domain when configurable threshold values are met or
exceeded per tenant application:

-   Server Utilization
    -   CPU utilization
    -   RAM utilization
    -   Physical memory usage
    -   Network bandwidth I/O utilization in Mbps
    -   Disk I/O utilization in IOPS
    -   Storage access time in milliseconds
    -   Logical storage usage

-   LAN Utilization
    -   Bandwidth utilization
    -   Routers/Switches including utilization, errors, and outages
    -   Connectivity status (up/down) in context of the network topology

-   Service Performance
    -   Total Number of Service Outages (by day or month)
    -   Aggregate Availability (most recent calendar month, most recent
        12 months)

Alarms generated by the computing infrastructure Monitoring and Control
Capability must identify the associated operating domain affected
services (by unique service identifier), and the tenant application.

The computing infrastructure Monitoring and Control Capability must
distinguish real-time performance data and summary-level performance
over specific time intervals (e.g., daily, monthly, etc.) by the
associated operating domain.

The computing infrastructure Monitoring and Control Capability must be
scalable as the number of services or the size of services (as defined
by the magnitude of the demand for the Cloud Service resource) increases
or decreases. In this context, “scalable” means that the computing
infrastructure Monitoring and Control function continues to perform as
required and is not adversely impacted.

Requirements for monitoring specific to the security are defined in CCSD
Section 8.3.

### 8.2 Cloud Service Performance Monitoring Capability

The FCS Monitoring and Control Function must implement an automated
Cloud Service Performance Monitoring Capability. The Cloud Service
Performance Monitoring Capability must track resource consumption by
tenant applications and monitor the performance on individual services
relative to the associated performance specifications and applicable SLA
provisions as defined in Attachment J-6. The Cloud Service Performance
Monitoring Capability must aggregate or roll-up resource consumptions
and service performance monitoring to the operating domain and physical
computing environment level.

The Cloud Service Performance Monitoring Capability must be scalable as
the number of services or the size of services (as defined by the
magnitude of the demand for Cloud Service resource) increases or
decreases. In this context, “scalable” means that the Cloud Service
Performance Monitoring Capability continues to perform as required and
is not adversely impacted as the number of cloud services increases.

The Cloud Service Performance Monitoring Capability must monitor usage
and provide alarms applicable on the following performance parameters
when threshold values are met or exceeded per tenant application:

-   Server Utilization

    -   CPU utilization

    -   RAM utilization

    -   Physical memory usage

    -   Network bandwidth I/O utilization in Mbps

    -   Disk I/O utilization in IOPS

    -   Storage access time in milliseconds

    -   Logical storage usage

<!-- -->

-   LAN Utilization

    -   Bandwidth utilization

    -   Routers/Switches including utilization, errors, and outages

    -   Connectivity status (up/down) in context of the network topology

<!-- -->

-   Service Performance

    -   Total Number of Service Outages (by day or month)

    -   Aggregate Availability (most recent calendar month, most recent
        12 months)

All alarms generated by the Cloud Service Performance Monitoring
Capability must uniquely identify the affected service by its unique
service identifier.

The Cloud Service Performance Monitoring Capability must support the
configuration of the severity levels for each type of alarm.

The Cloud Service Performance Monitoring Capability must implement the
ability to filter and sort alarms based upon the physical computing
environment, operating domain, tenant application, or specific subsets
of services.

The Cloud Service Performance Monitoring Capability must implement the
ability to specify a configurable usage warning level for on-line
network storage, archived storage, and remote storage services in terms
of the utilization percentage.

The FCS must warn/alert the tenant application via the API or the online
performance monitoring user interface if the tenant application is
exceeding 80% (configurable value) of the ordered on-demand virtual
instances and/or RAM threshold.

### 8.3 Cloud Security Monitoring Capability

The FCS Monitoring and Control Function must implement an automated
Cloud Security Monitoring Capability that detects and provides alarms of
security attacks, unauthorized access attempts, network intrusions, and
all other FedRAMP and FAA required monitoring information.

The Cloud Security Monitoring Capability must baseline behavior patterns
of tenant applications. The Cloud Security Monitoring Capability must
detect patterns that do not conform to the established baseline behavior
and provide alarms to security operators.

The Cloud Security Monitoring Capability must perform vulnerability
scans of physical computing environment and make the results available
to security operators consistent with FedRAMP requirements.

The Cloud Security Monitoring Capability must collect, log, and maintain
forensic data to support the analysis of security incidents, threat
assessments, and the extent to which unauthorized access may have been
gained to tenant applications and data. The data retention period must
be maintained online for 90 days. Depending on the nature of the
request, the forensic data must include one or more of the following at
a minimum: Security logs, VM snapshots, network access data, common
reference time synchronization for the forensic data and any other
information required to interpret the data. 

#### 8.3.1 Logging

The FCS Monitoring and Control Function must implement Logging
capability to collect and maintain separate logs for faults, alarms,
status, and performance.

The logs must be accessible by authorized personnel via the FCS
Performance Monitoring User Interface or the FCS Security Operations
On-line User Interface depending on the nature of the data.

The logs must be provided in Syslog format.

The on-line and off-line logs must be accessible to the Government as
defined in the PWS paragraph C.4.9.4.

----------------------------------------------------

## 9. On-line User Interfaces Requirements

The FCS must provide on-line user interfaces for Government-authorized
users to:

-   perform automated Account Management (e.g. account creation,
    deletion, suspension, roles, etc.) including service ordering,
    self-service provisioning, and service management as required by PWS
    paragraphs C.4.5.2 and C.4.5.3;

-   obtain the Performance Monitoring status of services within the
    physical computing environment at the enterprise level, at the
    operating domain level and at the individual tenant applications
    level;

-   obtain the Security Operations status of services within the
    physical computing environment at the enterprise level (summary
    level information), at the operating domain level, and at the
    individual tenant applications level.

The on-line user interfaces for FCS Performance Monitoring and Security
Operations status must be available both as a browser client and as a
real-time data feed that can be integrated with FAA enterprise Network
Operations Centers and Security Operations Centers.

The on-line user interfaces must be compatible with the current and
future versions of the Government’s default web browser (currently
Internet Explorer v.8.0, Google Chrome v.35.0.1916.153m, or later
versions). Secure connections from the Government’s web browser to the
FCS on-line user interfaces must utilize the Secure Sockets Layer (SSL)
or Secure Shell (SSH) protocols.

The on-line user interfaces or any web content must comply with the Web
Content Accessibility Guidelines (WCAG) 2.0 and the accessibility
standards (36 CFR Part 1194) under Section 508 of the Rehabilitation
Act:

-   §1194.21 Software applications and operating systems.
-   §1194.22 Web-based intranet and internet information and applications.
-   §1194.31 Functional performance criteria.
-   §1194.41 Information, documentation, and support.

Each distinct on-line user interface (Account Management, Performance
Monitoring, and Security Operations) must have a login for user access.
Each distinct on-line user interface must meet the Level\_1 performance
level as defined in CCSD Sections 3.2 through 3.4.

Access to the on-line user interfaces must be controlled via a
Government-approved credential and authentication management system. The
FCS on-line user interfaces must support user and role provisioning and
deprovisioning, and support Security Assertion Markup Language (SAML)
based authentication. The FCS on-line user interfaces must be
interoperable with the FAA’s credential and authentication management
system that uses centralized authority for user-to-system and
machine-to-machine authentication.

Each distinct on-line user interface must support multiple different
user privilege groupings as needed to control access to the data and
functions provided by the particular user interface. User interface
functions and specific subsets of data can be mapped to more than one
user privilege grouping. The on-line user interfaces must provide
role-based access control based upon user privilege groupings as
follows:

1)  Explicit authorization must be required for a user to perform any
    function within a given user privilege grouping.

2)  Users must be permitted to access functions in those user privilege
    groupings to which they have explicitly been granted access.

3)  Users can be granted access to more than one user
    privilege grouping.

4)  Access privileges must be distinguishable by the tenant application,
    operating domain, physical computing environment, and any
    combination or multiples of these attributes.

### 9.1 Account Management User Interface

The FCS must provide an on-line Account Management User Interface for
management of user accounts (tenant application developers and
owners[^2], the FCS Program Management Office (PMO), and other
stakeholders), service provisioning, and service management. The Account
Management User Interface must support all required ordering actions
defined in the PWS paragraph C.4.5.2.1. The Account Management User
Interface must provide the following capability and functions to
Government-authorized users based upon their access privileges:

1)  Automate account registration and approval process.

2)  Account management (e.g. suspend, delete, change
    roles/privileges, etc. of accounts based on roles and
    access privileges)

3)  Services management (e.g. create/add/modify/submit orders for
    services; discontinuing of ordered services).

4)  Services operations to include but not limited to:

    a.  Installing VM images and operating systems (except for OS
        ordered via the supplemental feature)

    b.  Attaching or detaching on-line network storage

5)  Modify the state of VMs (e.g. shutdown, running) and other services,
    and dashboard and customized reporting to include but not limited
    to:

    a.  Obtaining a service inventory listing of all tenant applications
        and associated ordered services by physical computing
        environment and operating domain for the current point in time,
        historical point in time, or a specific date range. When a date
        range is specified, the inventory listing must include all
        services that were in-service for any portion of the specified
        date range.

    b.  Obtaining customizable summary-level dashboard views and reports
        on the performance history[^3] of specific services supporting
        tenant applications and operating domains. The reports must be
        customizable with respect to the beginning and end dates of the
        performance interval, the services, and the performance measures
        covered by the report.

    c.  Reviewing detailed and summary level service billing information
        for specific tenant applications and operating domains.

    d.  Exporting custom-generated reports and any predefined reports
        available through the user interface

The Account Management User Interface must support Government-defined
ordering processes including the ingest, tracking, and display of
Government-specified data elements required to order and invoice,
services and uniquely associate them with individual tenant programs.

The Account Management User Interface must provide an on-line help
function explaining the user interface and the workflow.

The Account Management User Interface must provide the capability to
export the account management data to Microsoft Excel compatible format
for off-line analysis.

The Account Management User Interface must support at least 50
simultaneous user login sessions.

The Account Management User Interface must control access to the tenant
account information and service information for the individual operating
domains based upon access privileges.

### 9.2 Performance Monitoring User Interface

The FCS must provide an on-line Performance Monitoring User Interface
for access by Government-authorized users to the real-time performance
status and summary level metrics related to the FCS operating domains
and tenant applications.

The Performance Monitoring User Interface must provide the following
information:

1)  Real-time and archived alarms of performance issues that are mapped
    to affected services/tenants;

2)  Resource utilization data;

3)  Tenant Application/Service inventory information including service
    configuration information;

4)  Visibility into the status of corrective actions being taken by the
    Contractor;

5)  Performance summary dashboard/reports that are customizable by the
    user with respect to content and format; and

6)  Configuration of metrics and alarm thresholds

7)  Visibility into logical views and associated alarms and performance
    data provided through the use of the MaaS supplemental feature by
    tenant application agents.

8)  For Private physical computing environments only, visibility into
    the same status and performance data available to the Contractor
    operational personnel

The Performance Monitoring User Interface must support at least 50
simultaneous user login sessions.

The Performance Monitoring User Interface must provide an on-line help
function explaining the user interface and the workflow.

The Performance Monitoring User Interface must control access to the
performance status information for the individual operating domains
based upon access privileges.

The Performance Monitoring User Interface must provide users with the
ability to submit trouble ticket reports and view the status and
disposition of all user-generated, Contractor-generated or
system-generated trouble tickets.

The Performance Monitoring User Interface must allow users to define
filters to limit the alarms that are displayed. A user must be able to
define alarm filters based on the following criteria, either
individually or in combination to include, but not limited to:

1)  Severity level[^4];

2)  Services supporting specific tenant applications (by unique
    identifier assigned to each tenant, e.g., tenant account number)

3)  Tenant applications that exceed specific resource usage thresholds

4)  Operating domains and physical computing environments

5)  Alarm category

The Performance Monitoring User Interface must provide performance
status information relative to applicable SLA parameters.

The Performance Monitoring User Interface must provide for analyzing
usage trends as they relate to services supporting individual tenant
applications or individual elements of the physical computing
environment/operating domains.

#### 9.2.1 Alarms

The Performance Monitoring User Interface must provide alarms for the
following conditions:

-   Loss of Consumer/Provider connectivity

-   Configuration changes to the physical computing
    environment/operating domains

-   User-specified conditions/thresholds met or exceeded

The Performance Monitoring User Interface must provide the ability to
filter alarms based upon severity level, operating domain, tenant
application, or specific subsets of services.

The Performance Monitoring User Interface must be capable of displaying
multiple real-time alarms or events concurrently and of archived data of
up to 180 days.

The Performance Monitoring User Interface must provide the ability to
sort by severity. Only the high alarms must be acknowledged. An alarm
disappears after the state returns to normal and, in the case of high
alarms only, when the alarm has been acknowledged.

The Performance Monitoring User Interface must refresh the display of
Medium, Low, and High Information alarms without operator interaction
such that they are no longer displayed when the state returns to normal.
Filters can filter out all alarms except for high alarms.

#### 9.2.2 Report Generation

The Performance Monitoring User Interface must provide users with the
ability to obtain customizable reports on the performance of services
supporting specific tenant applications and operating domains. The
reports must be customizable for the services and the performance
measures covered by the report.

The Performance Monitoring User Interface must provide standardized and
customizable daily and historical (up to 180 days) summary reports of
service outages, alarms, and trouble tickets for all services, specific
groupings of services, and specific operating domains.

The Performance Monitoring User Interface must provide the capability to
export usage and performance data (based on user access privileges) to
Microsoft Excel compatible format for off-line analysis.

### 9.3 Security Operations User Interface

The FCS must provide secure access to on-line Security Operations User
Interface for Government authorized users to view the security status of
the services supporting specific FCS tenant applications, operating
domains, and physical computing environments (summary level
information). These interfaces must be separate for each physical
computing environment and operating domain. The FCS cloud management
interface must comply with the security requirements defined in CCSD
Section 4.4.

The Security Operations User Interface must provide an on-line help
function explaining the user interface and the workflow.

The Security Operations User Interface must be accessible by
Government-designated operational points-of-contact through a Web Portal
(i.e., web-enabled) interface.

The Security Operations User Interface must provide access to and
automated delivery of real-time and archived forms of security-related
events and alarms applicable to FCS tenant applications.

The Security Operations User Interface must support at least 20
simultaneous user login sessions.

----------------------------------------------------

## Appendix A - Tier III Facility Standards

A brief summary of items for Uptime Institute Tier III level is
presented in this Appendix. The Tier Standard is defined in detail in
the Uptime Institute document: *Data Center Site Infrastructure Tier
Standard: Topology.* Additional information that relates to Maintenance
and Operations is contained in *Data Center Site Infrastructure Tier
Standard: Operational Sustainability.*

NOTE: The availability figure that is sometimes used to represent Tier
III level topology is not a part of the Tier Standard. The 99.98%
availability is rather a byproduct of a data center infrastructure
topology that meets the Tier III standard. A guarantee of that level of
availability, without the corresponding topology design for concurrent
maintainability of the infrastructure, should not be used to claim Tier
III “self-certification.”

The FCS Checklist for the Tier III Facility Level Standards for
Self-Certification:

A.  Power System Design Standards: Power sources and power distribution
    in a data center must include the following:

-   Redundant power capacity and power distribution components

<!-- -->

-   Multiple independent power distribution paths serving the critical
    environment

-   At least one active and one alternate electrical power source that
    can each independently provide full data center power to IT
    equipment and cooling systems

-   At least one active and one alternate distribution path for power,
    each capable of sustaining the full IT environment

-   At least two backup generators with continuous duty rating, capable
    of supplying power to the site infrastructure

-   Twelve hours of on-site fuel storage for the generators

-   Planned maintenance can be performed on any power component without
    needing downtime for the IT processing environment

-   Automatic failover of power to deliver continual uninterrupted power
    to the IT environment

-   Documentation and drawings of current power system topology
    describing each major power system component and its associated
    configuration

-   Self-certification in accordance with the Uptime Institute Tier III
    compliance for power system topology and availability at 99.98%

A.  Cooling System Infrastructure Design Standards: Cooling sources and
    cooling distribution paths in a data center must include the
    following:

-   Redundant cooling capacity and cooling distribution components

-   Multiple independent cooling distribution paths serving the critical
    environment

-   At least one active and one alternate cooling source that can each
    independently provide adequate heat rejection for the critical IT
    environment

-   At least one active and one alternate distribution path for cooling,
    each capable of cooling the critical IT environment

-   Planned maintenance can be performed on any cooling component
    without needing downtime for the IT processing environment

-   Automatic failover of cooling to the backup system to deliver
    continual, uninterrupted cooling is delivered to the IT environment

A.  Availability of power and cooling infrastructure at 99.98 % for
    self-certification in addition to the above items for
    topology design.

B.  Scheduled or unscheduled downtime is not needed for power system and
    cooling system maintenance or emergency repairs.

[^1]: Specifications for MaaS capabilities will be determined on an
    Individual Case Basis and will be added through contract
    modifications.

[^2]: A tenant application “owner” is the Government-designated
    point-of-contact for a tenant application in the test, operations,
    or support phase of its life cycle.

[^3]: Customizable reports available through the Account Management User
    Interface are historical in nature looking back over performance
    since service inception. Real-time status information is provided
    through the Performance Monitoring User Interface.

[^4]: Excludes the ability to filter out the highest severity level of
    alarms.
