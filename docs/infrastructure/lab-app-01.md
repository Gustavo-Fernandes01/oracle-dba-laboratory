# 🖥️ LAB-APP-01 — Application Server Infrastructure

## 1. Overview
This virtual machine serves as the Application Server defined in the initial architecture. It is designed to host the application layer completely separated from the database layer to prevent resource contention.

| Parameter | Configuration |
| :--- | :--- |
| **Host OS** | Windows 11 Pro |
| **Hypervisor** | Oracle VirtualBox |
| **Guest OS** | Oracle Linux Server 8.10 x86_64 |
| **vCPU / RAM** | 2 vCPU / 4 GB RAM |
| **Storage** | 40 GB |
| **Network** | Bridged Adapter |
| **IP / Subnet** | `10.0.0.253/24` (Gateway `10.0.0.1`) |
| **Hostname** | `LAB-APP-01` |
| **Security** | SELinux: Enforcing \| `firewalld`: Active (Only default SSH validated) |

## 2. Current Status & Application Stack
**Infrastructure operational / Java 17 Operational / Application stack in progress.**
* **Java:** Oracle JDK 17.0.12 LTS (Operational)
* **ORDS:** ORDS 23.4 (Planned)
* **APEX:** Oracle APEX 22.2 (Planned)

*(Note: ORDS and APEX are planned but NOT yet implemented).*

## 3. Connectivity Validation
Network connectivity between the Application Server and the Database Server has been successfully validated via ping:
* `LAB-APP-01 (10.0.0.253)` ➔ `LAB-DB-01 (10.0.0.254)`: **SUCCESS**

*(Note: This validates OS-level infrastructure connectivity only. Application-level database connections are not yet established).*

## 4. Hypervisor Snapshots
1. `baseline-lab-app-01`: Baseline after LAB-APP-01 infrastructure provisioning and validation. Before installation of Java, ORDS, and APEX.
2. `java-17-functional-baseline`: Functional baseline after installation and validation of Oracle JDK 17 LTS on LAB-APP-01. Before ORDS installation.
