# Operating System Selection

## Decision

Oracle Linux was selected because it provides strong alignment with the Oracle 
technology stack used throughout the laboratory and is an Oracle-supported Linux 
platform for the database environment.

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

## Decision Rationale

Oracle Linux was selected because it provides a strong alignment with the
Oracle technology stack used throughout the laboratory.

Using Oracle Linux on both servers also provides an operationally consistent
environment. System administration, service management, networking,
permissions, package management and troubleshooting can follow the same
operational model across the infrastructure.

Windows Server was not selected because the initial architecture does not
require Microsoft-specific services or workloads.

Ubuntu Server and Red Hat Enterprise Linux remain relevant alternatives and
may be evaluated in future experiments.

## Operational Consistency

Using the same Linux distribution on both servers reduces unnecessary
variation in the initial environment.

This allows the laboratory to focus on the behavior of the database,
application and data infrastructure rather than introducing differences in
operating system administration between servers.

The decision does not imply that using a single operating system is always
preferable in production environments. Operating system selection should
always depend on workload requirements, vendor support, organizational
standards and operational constraints.

## Future Evaluation

The laboratory may later conduct a controlled comparison between different
Linux distributions.

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

**Selected OS: Oracle Linux**
