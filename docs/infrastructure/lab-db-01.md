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
**Infrastructure operational / Application stack pending.**
* **Java:** Java 21 LTS (Planned)
* **ORDS:** ORDS 26.1.1+ (Planned)
* **APEX:** Oracle APEX 26.1 (Planned)

*(Note: These components are planned but NOT yet implemented. No application ports have been opened yet).*

## 3. Connectivity Validation
Network connectivity between the Application Server and the Database Server has been successfully validated via ping:
* `LAB-APP-01 (10.0.0.253)` ➔ `LAB-DB-01 (10.0.0.254)`: **SUCCESS**

*(Note: This validates OS-level infrastructure connectivity only. Application-level database connections are not yet established).*

## 4. Hypervisor Snapshots
1. `baseline-lab-app-01`: Baseline after LAB-APP-01 infrastructure provisioning and validation. Before installation of Java, ORDS, and APEX.
