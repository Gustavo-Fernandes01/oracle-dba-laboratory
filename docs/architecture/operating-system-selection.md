# Operating System Selection

## Decision

Oracle Linux 8.10 (x86_64) was selected as the operating system for both
infrastructure servers in the initial laboratory architecture.

The servers will use the Oracle Unbreakable Enterprise Kernel (UEK) provided
with Oracle Linux 8.10.

The decision prioritizes compatibility with the Oracle technology stack,
operational consistency, security updates, maintainability and future
evolution of the laboratory.

## Context

The laboratory will initially contain two virtual machines:

- Database Server
- Application Server

The Database Server will host Oracle Database 21c XE.

The Application Server will host Oracle APEX, Oracle REST Data Services
(ORDS), Java and the application layer.

The infrastructure is being designed around Oracle technologies while
maintaining the possibility of introducing Data Engineering and Infrastructure
technologies in later phases.

## Alternatives Considered

The main operating system alternatives considered were:

- Oracle Linux
- Ubuntu Server
- Red Hat Enterprise Linux
- Windows Server

Oracle Linux releases considered included:

- Oracle Linux 8
- Oracle Linux 9
- Oracle Linux 10

## Decision Rationale

Oracle Linux was selected because it provides strong alignment with the
Oracle technology stack used throughout the laboratory and is an Oracle
supported Linux platform for the database environment.

Using Oracle Linux on both servers also provides an operationally consistent
environment. System administration, service management, networking,
permissions, package management and troubleshooting can follow the same
operational model across the infrastructure.

Windows Server was not selected because the initial architecture does not
require Microsoft-specific services or workloads.

Ubuntu Server and Red Hat Enterprise Linux remain relevant alternatives and
may be evaluated in future experiments.

## Oracle Linux Version Selection

Oracle Linux 8.10 was selected instead of a newer major release because the
laboratory's primary database platform is Oracle Database 21c XE.

The official Oracle Database 21c XE documentation provides an installation
path for Oracle Linux 8, including the Oracle Database 21c XE RPM package and
the corresponding preinstallation package.

Oracle Linux 8.10 represents the latest update level of the Oracle Linux 8
family and provides current maintenance, security updates and improvements
while remaining within the Oracle Linux 8 platform family used by the
database environment.

The laboratory therefore prioritizes a supported and reproducible software
stack over simply selecting the newest available major operating system
release.

## Kernel Selection

Oracle Linux 8.10 uses the Oracle Unbreakable Enterprise Kernel (UEK) as its
Oracle-provided enterprise kernel option.

For new Oracle Linux 8.10 x86_64 installations, UEK R7 is provided as the
default kernel.

UEK R7 provides a modern kernel environment while maintaining alignment with
the Oracle Linux platform.

The laboratory will therefore initially use:

- Operating System: Oracle Linux 8.10
- Architecture: x86_64
- Kernel: Oracle Unbreakable Enterprise Kernel R7

The exact kernel build installed on the system will be recorded after the
operating system installation.

## Operational Consistency

Using the same Linux distribution and release family on both servers reduces
unnecessary variation in the initial environment.

This allows the laboratory to focus on the behavior of the database,
application and data infrastructure rather than introducing differences in
operating system administration between servers.

The decision does not imply that using a single operating system is always
preferable in production environments. Operating system selection should
always depend on workload requirements, vendor support, organizational
standards and operational constraints.

## Initial Virtual Machine Configuration

The selected operating system will initially be deployed on two virtual
machines running through Oracle VirtualBox.

### VM 01 — Database Server

| Resource | Configuration |
|---|---|
| Purpose | Database Server |
| Operating System | Oracle Linux 8.10 x86_64 |
| CPU | 1 vCPU |
| RAM | 2 GB |
| Storage | 30 GB |
| Disk Type | VDI |
| Disk Allocation | Dynamically Allocated |
| Network | Bridged Adapter |
| IP Address | 10.0.0.254 |

The Database Server will initially host:

- Oracle Database 21c XE

The resource allocation is intentionally conservative due to the hardware
limitations of the physical host.

### VM 02 — Application Server

| Resource | Configuration |
|---|---|
| Purpose | Application Server |
| Operating System | Oracle Linux 8.10 x86_64 |
| CPU | 2 vCPU |
| RAM | 4 GB |
| Storage | 40 GB |
| Disk Type | VDI |
| Disk Allocation | Dynamically Allocated |
| Network | Bridged Adapter |
| IP Address | 10.0.0.253 |

The Application Server will initially host:

- Oracle APEX 26.1
- Oracle REST Data Services 25.3
- Java runtime
- Application services

The exact Java version will be determined during the implementation stage
according to the compatibility requirements of the selected ORDS version.

## Resource Constraints

The laboratory runs on a personal workstation with limited hardware
resources:

- CPU: Intel Core i5-3470 @ 3.20 GHz
- Physical cores: 4
- Logical processors: 4
- RAM: 16 GB
- Storage: SATA SSD + SATA HDD
- Hypervisor: Oracle VirtualBox

The virtual machines will primarily use the 1 TB SATA HDD for virtual disk
storage.

The virtual machines do not need to run simultaneously. Resource allocation
may be modified during future experiments according to workload requirements.

Resource allocation itself may become a subject of performance experiments.

## Future Evaluation

The laboratory may later conduct controlled comparisons between different
Linux distributions and operating system versions.

Potential evaluation criteria include:

- Resource consumption
- Performance
- Database compatibility
- Stability
- Administration
- Security
- Package management
- Automation
- Containerization
- Cloud compatibility
- Documentation and community support

The results may be documented as an independent technical experiment and
potentially developed into a technical article.

## Status

**Decision: Accepted**

**Selected OS: Oracle Linux 8.10 x86_64**

**Kernel: Oracle UEK R7**

**Database Server: LAB-DB-01**

**Application Server: LAB-APP-01**
