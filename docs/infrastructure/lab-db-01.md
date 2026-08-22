# 🖥️ LAB-DB-01 — Database Server Infrastructure

## 1. Overview
Dedicated server for the laboratory's Oracle Database. Designed to ensure resource isolation, data persistence, and reproducibility.

| Parameter | Configuration |
| :--- | :--- |
| **Host OS** | Windows 11 Pro |
| **Hypervisor** | Oracle VirtualBox |
| **Guest OS** | Oracle Linux Server 8.10 x86_64 |
| **Kernel** | Unbreakable Enterprise Kernel (UEK R7) |
| **vCPU / RAM** | 1 vCPU / 2 GB RAM |
| **Storage / Swap** | 30 GB (SATA HDD) / ~2 GB Swap |
| **Network** | Bridged Adapter (`enp0s3`) |
| **IP / Subnet** | `10.0.0.254/24` (Gateway `10.0.0.1`) |
| **Hostname** | `LAB-DB-01` |
| **Security** | SELinux: Enforcing | `firewalld`: Active | SSH: Enabled |

## 2. Oracle Database 21c XE
* **Version:** Oracle Database 21c Express Edition x86_64
* **ORACLE_SID:** `XE`
* **ORACLE_HOME:** `/opt/oracle/product/21c/dbhomeXE`
* **ORACLE_BASE:** `/opt/oracle`
* **Configured Ports:** `1521` (TCP Listener) | `5500` (Local EM Express)
* **Topology:** CDB (`XE`) with default PDB (`XEPDB1`)

## 3. System and Connectivity Validation
* `XE` instance in `OPEN` state and database in `READ WRITE` mode.
* `XEPDB1` container in `READ WRITE` state.
* Listener is active and successfully registering the `XE`, `XEXDB`, and `xepdb1` services.
* Local connection `sqlplus / as sysdba` validated via the `oracle` OS user.
* Remote/Listener connection `system@localhost:1521/xepdb1` validated.
* `oracle-xe-21c` systemd service configured for automatic startup on boot.

## 4. Hypervisor Snapshots
1. `baseline-oracle-linux-8.10-uek-r7`: Base OS and static network configured prior to database installation.
2. `oracle-xe-21c-functional-baseline`: Full functional installation and validation of Oracle XE.
