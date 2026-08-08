# Project Definition

> **Project Status:** Planning / Phase 01 — Infrastructure Foundation

## 1. Objective

The objective of this laboratory is to build a professional and reproducible
data infrastructure using modern technologies related to Database Systems,
Data Engineering, Cloud and Infrastructure.

The laboratory is designed as a practical learning environment where different
architectures, technologies and configurations can be implemented, tested,
measured and documented.

The project will focus not only on making systems work, but also on
understanding their behavior, identifying bottlenecks and evaluating possible
optimizations.

---

## 2. Problem

The main problem investigated by this laboratory is:

> How can a data infrastructure be designed, implemented and optimized to
> efficiently, reliably and scalably process, store and provide data?

Performance and optimization will be important areas of experimentation
throughout the project.

The laboratory will allow different architectural approaches to be compared
through practical experiments and measurements.

---

## 3. Scope

The laboratory will progressively cover the following areas:

- Database Systems
- Database Administration
- SQL
- Linux Infrastructure
- Networking
- Data Engineering
- ETL / ELT
- Data Pipelines
- Data Warehousing
- Data Lakes
- Workflow Orchestration
- Distributed Data Processing
- Cloud Infrastructure
- Performance Engineering
- Observability
- Security
- Infrastructure as Code
- Containerization
- Distributed Systems

The scope is intentionally evolutionary.

New technologies will only be introduced when they provide a meaningful
technical or educational purpose.

---

## 4. Functional Requirements

The laboratory should:

- Provide a functional database infrastructure.
- Support data ingestion.
- Support data transformation.
- Support ETL / ELT processes.
- Support automated data pipelines.
- Allow performance experiments.
- Allow comparison between different architectures.
- Document relevant configurations and experiments.
- Allow the environment to be reproduced whenever practical.

---

## 5. Non-Functional Requirements

The laboratory should prioritize:

### Performance

The infrastructure should allow performance to be measured and analyzed.

### Scalability

The architecture should allow experiments involving the expansion or
separation of components.

### Security

Credentials, secrets and sensitive information must never be committed
to the public repository.

### Reproducibility

Configurations and procedures should be documented so that the environment
can be rebuilt whenever practical.

### Observability

Relevant logs, metrics and system behavior should be monitored whenever
appropriate.

### Modularity

Components should be separated when doing so provides a technical or
educational benefit.

### Cost

The project should prioritize free, open-source or officially free-tier
technologies whenever appropriate.

---

## 6. Constraints

The laboratory will initially run on a personal computer with the following
hardware configuration:

- Host operating system: Windows 11 Pro
- CPU: Intel Core i5-3470 @ 3.20 GHz
- Physical cores: 4
- Logical processors: 4
- RAM: 16 GB
- Storage: SATA SSD + SATA HDD
- Virtualization: Enabled
- Hypervisor: Oracle VirtualBox

The host system has limited CPU resources and therefore the laboratory must
carefully manage CPU and memory allocation across virtual machines.

Virtual machines do not need to run simultaneously. Components may be
started and stopped according to the experiment being performed.

Linux will be the preferred operating system for infrastructure components
when technically appropriate.

Resource consumption and performance may themselves become subjects of
experimentation throughout the laboratory.

---

## 7. Technologies

The laboratory will prioritize current, relevant, free or open-source
technologies, as well as officially available free-tier technologies.

The initial technology stack includes:

- Oracle Database 21c XE
- Oracle APEX 26.1
- Oracle REST Data Services 25.3
- JDK 26
- SQL Developer 24.3.1
- Linux
- Python
- Apache Airflow
- Apache Spark / PySpark
- Docker
- Terraform
- Git
- GitHub
- Oracle Cloud Infrastructure
- AWS

The technology stack may evolve throughout the project.

Technologies will not be introduced simply because they are popular.
Each technology should have a clear technical or educational purpose.

---

## 8. Initial Architecture Hypothesis

The initial architecture will be developed incrementally.

The project will initially focus on building and understanding the database
infrastructure.

The architecture may then evolve through stages such as:

1. Database Server
2. Application Server
3. Separation of application and database services
4. Load balancing
5. Data Engineering services
6. Orchestration
7. Distributed processing
8. Cloud infrastructure
9. Distributed and highly available architectures

Each architectural evolution should be analyzed before and after its
implementation.

Where possible, experiments should include measurements, comparisons and
technical justification.

---

## 9. Success Criteria

The laboratory will be considered successful when it demonstrates:

- A functional and documented infrastructure.
- Practical knowledge of database systems.
- Practical experience with data engineering concepts.
- Practical experience with infrastructure and cloud technologies.
- Ability to perform and analyze performance experiments.
- Ability to compare architectural alternatives.
- Proper version control practices.
- Reproducible configurations whenever practical.
- Technical documentation of decisions and experiments.
- The ability to explain and justify architectural decisions.

A major goal is not simply to make the infrastructure work, but to understand
why each architectural decision was made.

---

## 10. Roadmap

### Phase 01 — Infrastructure Foundation

- VirtualBox
- Linux
- Networking
- Database VM

### Phase 02 — Database

- Oracle Database
- SQL
- Schema design
- Performance
- Backup and Recovery

### Phase 03 — Application Layer

- ORDS
- APEX
- Application Server
- APIs

### Phase 04 — Data Engineering

- Python
- ETL / ELT
- Data Pipelines
- Data Modeling

### Phase 05 — Orchestration

- Apache Airflow
- Workflow automation

### Phase 06 — Data Platform

- Data Warehouse
- Data Lake
- Object Storage

### Phase 07 — Big Data

- Apache Spark
- PySpark
- Distributed Processing

### Phase 08 — Cloud

- Oracle Cloud Infrastructure
- AWS
- Cloud Data Services

### Phase 09 — Production Engineering

- Docker
- CI/CD
- Terraform
- Security
- Monitoring
- Data Quality

### Phase 10 — Distributed Systems

- Scalability
- Load Balancing
- Replication
- Fault Tolerance
- Performance Engineering

---
## Engineering Principles

The laboratory follows a few core principles:

- Understand before implementing.
- Prefer measurable results over assumptions.
- Introduce technologies only when there is a clear purpose.
- Document important architectural decisions.
- Measure performance before and after significant changes.
- Treat failures and unexpected results as part of the learning process.
- Prefer reproducible configurations whenever practical.
- Keep security practices from the beginning of the project.

---

## Learning Methodology

The laboratory follows an iterative learning methodology.

When a project stage requires knowledge that has not yet been acquired,
implementation will be temporarily paused.

The required concept will then be studied and practiced before returning
to the project.

The cycle is:

Project → Knowledge Gap → Study → Practice → Implementation → Experiment →
Analysis → Documentation
