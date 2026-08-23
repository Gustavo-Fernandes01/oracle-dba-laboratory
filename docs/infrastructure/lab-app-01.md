# 🖥️ LAB-APP-01 — Application Server Infrastructure

## 1. Overview
This virtual machine serves as the Application Server defined in the initial architecture. It is designed to host the application layer completely separated from the database layer to prevent resource contention.

## 2. Virtual Machine
* **Hostname:** `LAB-APP-01`
* **OS:** Oracle Linux Server 8.10
* **Architecture:** x86_64
* **CPU:** 2 vCPU
* **RAM:** 4 GB
* **Storage:** 40 GB
* **Hypervisor:** Oracle VirtualBox
* **Network Mode:** Bridged Adapter

## 3. Network
* **Interface:** Bridged Networking
* **IPv4 (Static):** `10.0.0.253`
* **Subnet:** `/24` (`255.255.255.0`)
* **Gateway:** `10.0.0.1`
* **Persistence:** Static IP configuration is persistent across reboots via NetworkManager.

## 4. Security Baseline
* **SELinux:** Enforcing
* **firewalld:** Active (Only default SSH access is currently validated; no additional application ports have been opened yet).

## 5. Connectivity
Network connectivity between the Application Server and the Database Server has been successfully validated via ping:
* `LAB-APP-01 (10.0.0.253)` ➔ `LAB-DB-01 (10.0.0.254)`: **SUCCESS**

*(Note: This validates OS-level infrastructure connectivity only. Application-level database connections are not yet established).*

## 6. Snapshot
* **Name:** `baseline-lab-app-01`
* **Description:** Baseline after LAB-APP-01 infrastructure provisioning and validation. Before installation of Java, ORDS, and APEX.

## 7. Current Status
**Infrastructure operational / Application stack pending.**
*(Java 21, ORDS 26.1.1+, and APEX 26.1 are Planned but NOT yet implemented).*
