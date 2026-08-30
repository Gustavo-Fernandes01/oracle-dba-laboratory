# ☕ Oracle JDK 17 Setup & Validation

## 1. Overview
Java 17 LTS is the officially selected and implemented runtime for the Application Server (`LAB-APP-01`). It serves as the foundational layer required for the future installation of Oracle REST Data Services (ORDS 23.4).

## 2. Server Context
* **Hostname:** `LAB-APP-01`
* **IP Address:** `10.0.0.253`
* **OS:** Oracle Linux Server 8.10 x86_64

## 3. Version & Implementation
* **Implementation:** Oracle JDK
* **Version:** 17.0.12 LTS
* **RPM Package:** `jdk-17-2000:17.0.12-8.x86_64`
* **Installation Path:** `/usr/lib/jvm/jdk-17.0.12-oracle-x64`

## 4. Installation Method & Integrity
* Installed via the official Oracle RPM: `jdk-17.0.12_linux-x64_bin.rpm`.
* Installed cleanly after restoring the node to `baseline-lab-app-01`.

## 5. Environment Configuration
The Java environment is fully persistent across sessions.
* **Global configuration:** `/etc/profile.d/java_home.sh`
* **User configuration:** `~/.bashrc` (for user `gustavo`)
* **JAVA_HOME:** `/usr/lib/jvm/jdk-17.0.12-oracle-x64`

## 6. Validation Evidence
The runtime was validated in a new shell environment:

```bash
$ java -version
java version "17.0.12" 2024-07-16 LTS
Java(TM) SE Runtime Environment (build 17.0.12+8-LTS-286)
Java HotSpot(TM) 64-Bit Server VM (build 17.0.12+8-LTS-286, mixed mode, sharing)

$ which java
/usr/bin/java

$ readlink -f "$(which java)"
/usr/lib/jvm/jdk-17.0.12-oracle-x64/bin/java

$ echo $JAVA_HOME
/usr/lib/jvm/jdk-17.0.12-oracle-x64
```
*System state post-installation: SELinux remains Enforcing, firewalld is Active, and Networking is intact.*

## 7. Architectural Context & Current Status
* **Java 17 LTS:** Operational
* **ORDS 23.4:** Planned
* **APEX 22.2:** Planned

Java 17 LTS has been provisioned to align with the compatibility matrix required for ORDS 23.4, Oracle APEX 22.2, and Oracle Database 21c XE.
