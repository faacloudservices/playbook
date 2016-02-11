##Introduction to Tri-Modal Approach to Cloud Services

![Image of bicycle gear
shift]({{site.baseurl}}/assets/images/Bicycle_Drivetrain.png)

Unlike other cloud service delivery models, Infrastructure as a Service
provides a number of alternate onramps to the cloud that span from
minimizing changes and shipping existing on-premise VMs to full
refactoring of applications to take advantage of new cloud architectural
patterns. As a result, this document proposes and aligns IaaS standards
across a tri-modal approach to cloud services.

The first approach, called **Low Gear**, provides a minimum viable set of
standards for legacy applications migrating to the cloud with little to
no code or configuration changes. These applications are moving to the
cloud by simply exporting existing virtual machines images from on
premise ESXi environments as VMDK or OVF files and attaching the files
to service orders for CCSD 6.1.1 monthly-priced virtual machines using
the process outlined by section C.4.4.2.4 of the FCS contract. Once in
the cloud, a systems administrator boots the virtual machine, assigns
new IP addresses from the deployment environment's block of addresses,
and installs agents and client software to integrate with the Agility
Platform and other monitoring and control components in the cloud. This
approach offers the quickest and easiest path to migrating systems to
the cloud, but at the expense of carrying over complex images and
forgoing the flexibility to pursue more advanced features such as
horizontal scalability. Once in the cloud, the application is
operationally managed just as it is today, including manual testing,
manual deployment through the existing Dev/Test, Pre-Prod, Prod
pipeline.

The second approach, called **Medium Gear**, provides an interim set of
standards for legacy applications that benefit from refactoring onto
standard configurations of images and automation assets orderable from
the deployment environment's service catalog. These applications are
moving to the cloud through the process of re-implementing the
application architecture as an orchestration script that provides
automated deployment of the solution stack. This re-implementation is an
iterative development process of creating a new top-level orchestration
script using an existing catalog of "stem cell" base images and
automation assets. In the case of the FCS cloud environment, this is
done by creating a top-level Agility Blueprint through the Agility
Designer Tool using Agility blueprints, workloads, and packages. If
architecturally appropriate, these Agility Blueprints would implement
horizontal scaling through scaling plans that tie to CCSD 6.1.1
monthly-priced virtual machines with the operating system and elasticity
supplemental features. Once the application architecture is in place and
tested, a systems administrator manually migrates over the application
logic and data. Once in the cloud, the application logic and data is
operationally managed just as it is today, but all updates to the
underlying middleware and operating system are now handled as feature
requests and updates to the version-controlled blueprint and automation
assets that implement environment that the application runs on top of.

The third approach, called **High Gear**, provides standards for new and
existing applications that seek full adoption of agile methodologies as
outlined in the U.S. Digital Services Playbook. This extends the
automated deployment infrastructure involved in Medium Gear to a full
DevOps toolchain by adding continuous integration components and
automated testing. In the case of the FCS cloud environment, this DevOps
toolchain shall be managed by the Agility Release Manager. Depending on
the complexity of the application's architecture, a high-gear
application may elect to bypass the complexity of IaaS and implement a
microservices approach by deploying containers or alternate higher-level
deployment units using platform as a server (PaaS). Unlike traditional
applications, the full operational management of the application is
controlled by a strong product manager that controls the entire
deployment pipeline and manages work that spans agile development teams
and agile infrastructure teams. In order to execute on this new
approach, the FAA shall likely require a DevOps support team that can
perform direct action as a digital services team and provide DevOps Dojo
support to teach ADE and AIF personnel the cultural and technical
practices needed to establish agile development teams and agile
infrastructure teams with a common DevOps culture.