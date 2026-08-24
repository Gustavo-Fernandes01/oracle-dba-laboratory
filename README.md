# 🏛️ Oracle DBA & Data Engineering Laboratory

A repository dedicated to building, testing, measuring, and documenting a professional, reproducible, and scalable data infrastructure.

## 🏗️ Laboratory Architecture (Phase 01)

| Server | OS | Resources | Role | Status |
| :--- | :--- | :--- | :--- | :--- |
| **`LAB-DB-01`** | Oracle Linux 8.10 (UEK R7) | 1 vCPU / 2 GB RAM | Oracle Database 21c XE | 🟢 Operational |
| **`LAB-APP-01`** | Oracle Linux 8.10 (UEK R7) | 2 vCPU / 4 GB RAM | Java 21 / ORDS 26.1.1+ / APEX 26.1 | 🟡 Infra Operational / Java 21 Operational (ORDS/APEX Planned) |

---

## 📂 Repository Structure

```text
oracle-dba-laboratory/
├── README.md
├── docs/
│   ├── architecture/      # Architecture decisions and OS definitions
│   ├── infrastructure/    # Hardware, VMs, and network mapping
│   ├── database/          # Installation guides, tuning, and DB routines
│   ├── decisions/         # Architectural Decision Records (ADRs)
│   ├── experiments/       # Performance, load tests, and metrics
│   └── operations/        # Operational manuals and runbooks
├── scripts/               # Operational scripts (Bash/SQL)
└── automation/            # Automation playbooks (Ansible/Terraform)
```

## 🔗 Quick Reference Documentation
* [Project Definition](docs/architecture/project-definition.md)
* [Operating System Selection](docs/architecture/operating-system-selection.md)
* [Initial Architecture](docs/architecture/initial-architecture.md)
* [LAB-DB-01 Infrastructure](docs/infrastructure/lab-db-01.md)
* [Oracle 21c XE Setup & Validation](docs/database/oracle-21c-xe-setup.md)
