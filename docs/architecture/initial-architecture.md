# Initial Architecture

## Overview

The laboratory will initially use a two-server architecture implemented
through Oracle VirtualBox virtual machines.

The host system is a Windows 11 Pro workstation with limited hardware
resources. Therefore, the initial architecture prioritizes simplicity,
resource efficiency, service separation and gradual evolution.

The infrastructure will use Oracle Linux as the operating system for both
virtual machines.

The initial architecture separates database services from the application
layer.

---

## Host Environment

The laboratory will run on a personal workstation with the following
configuration:

- Host Operating System: Windows 11 Pro
- CPU: Intel Core i5-3470 @ 3.20 GHz
- Physical Cores: 4
- Logical Processors: 4
- RAM: 16 GB
- Storage: SATA SSD + SATA HDD
- Hypervisor: Oracle VirtualBox
- Virtualization: Enabled

The virtual machines will primarily use the 1 TB SATA HDD for virtual disk
storage in order to preserve SSD resources for the host operating system and
other workloads.

Because the host has limited CPU and memory resources, virtual machines will
not necessarily run simultaneously. The environment will be adjusted
according to the requirements of each experiment.

---

# Virtual Machines

## VM 01 — Database Server

The first virtual machine will be dedicated to database infrastructure.

### Operating System

- Oracle Linux

### Resources

- CPU: 1 vCPU initially
- RAM: 2 GB
- Storage: 30 GB
- Network: Bridged Adapter

### Main Services

- Oracle Database 21c XE

### Responsibilities

The Database Server will be responsible for:

- Persistent data storage
- Database management
- SQL execution
- Schema management
- Database performance experiments
- Backup and recovery experiments
- Database administration experiments

The database will remain isolated from the application layer to allow the
laboratory to analyze communication, performance and resource utilization
between separate infrastructure components.

---

## VM 02 — Application Server

The second virtual machine will host the application layer.

### Operating System

- Oracle Linux

### Resources

- CPU: 2 vCPU
- RAM: 4 GB
- Storage: 40 GB
- Network: Bridged Adapter

### Main Components

- Oracle APEX 26.1
- Oracle REST Data Services 25.3
- Java runtime
- Application layer

The exact Java version will be determined during the implementation stage
according to the compatibility requirements of the selected ORDS version.

### Responsibilities

The Application Server will be responsible for:

- Hosting Oracle APEX
- Running Oracle REST Data Services
- Providing application access to the database
- Exposing application services
- Supporting future API and application experiments

---

# Network Architecture

The virtual machines will initially use VirtualBox Bridged Networking.

With Bridged Networking, each virtual machine will appear as an independent
device on the physical network.

The physical network uses the 10.0.0.0/24 subnet.

The initial network configuration is:

| Component | Role | IP Address |
|---|---|---|
| Windows 11 Host | Virtualization Host | 10.0.0.6 |
| Home Router | Default Gateway | 10.0.0.1 |
| VM 01 | Database Server | 10.0.0.254 |
| VM 02 | Application Server | 10.0.0.253 |

Network parameters:

- Network: 10.0.0.0/24
- Subnet Mask: 255.255.255.0
- Default Gateway: 10.0.0.1
- Database Server: 10.0.0.254
- Application Server: 10.0.0.253

The Database Server and Application Server will use manually configured
addresses to provide predictable connectivity between infrastructure
components.

The server addresses will be configured inside the guest operating systems.
VirtualBox will provide network connectivity through the Bridged Adapter.

---

# Initial Communication Flow

The expected application flow is:

**User → Application Server → Oracle Database 21c XE**

The Application Server will be the main entry point for application-level
access.

The Database Server will not be directly exposed to end users.
Application-level access to the database will be mediated through the
Application Server.

---

# Resource Allocation

The initial resource allocation is intentionally conservative.

| Component | CPU | RAM | Storage |
|---|---|---|---|
| Windows 11 Host | 4 cores | 16 GB | SSD/HDD |
| Database Server | 1 vCPU | 2 GB | 30 GB |
| Application Server | 2 vCPU | 4 GB | 40 GB |

The remaining host resources will be reserved for Windows 11 and VirtualBox
overhead.

Resource allocation may be modified during performance experiments.

---

# Architectural Principles

The initial architecture follows the following principles:

## Separation of Concerns

Database and application responsibilities are placed on separate servers.

## Operational Consistency

Both servers use Oracle Linux, allowing system administration and
troubleshooting to follow a consistent operational model.

## Resource Awareness

Virtual machine resources are deliberately limited to reflect the
constraints of the physical host.

## Incremental Evolution

The architecture is intentionally simple at the beginning and will evolve
as new technical requirements are introduced.

## Reproducibility

Infrastructure configuration and architectural decisions should be
documented so that the environment can be rebuilt whenever practical.

---

# Future Evolution

The initial two-server architecture is not considered the final architecture.

Future iterations may introduce:

- Separate application services
- Load balancing
- Additional application servers
- Data ingestion services
- Python-based pipelines
- Apache Airflow
- Apache Spark / PySpark
- Data Warehouse
- Data Lake
- Object Storage
- Docker
- Infrastructure as Code
- Monitoring and observability
- CI/CD
- Security controls
- Replication
- Fault tolerance
- Cloud infrastructure
- Distributed systems

Each major architectural change should be preceded by an analysis of the
problem it is intended to solve.

Where practical, performance measurements should be collected before and
after the change.

---

# Current Status

**Architecture Status: Initial Design**

**Virtual Machines Planned: 2**

**Database Server: Oracle Linux**

**Application Server: Oracle Linux**

The architecture is approved for implementation, subject to final
verification of software compatibility requirements during the
implementation stage.
