# ☕ Oracle JDK 21 Setup & Validation

## 1. Overview
Java 21 LTS is the officially selected and implemented runtime for the Application Server (`LAB-APP-01`). It serves as the foundational layer required for the future installation of Oracle REST Data Services (ORDS).

## 2. Server Context
* **Hostname:** `LAB-APP-01`
* **IP Address:** `10.0.0.253`
* **OS:** Oracle Linux Server 8.10 x86_64

## 3. Version & Implementation
* **Implementation:** Oracle JDK
* **Version:** 21.0.12.1 LTS
* **RPM Package:** `jdk-21-21.0.12.1-1.x86_64`
* **Installation Path:** `/usr/lib/jvm/jdk-21.0.12.1-oracle-x64`

> **Note:** OpenJDK 21 was previously used as an intermediate runtime but was explicitly removed and replaced by the official Oracle JDK 21 to align with the Oracle-centric architecture.

## 4. Installation Method & Integrity
* Installed via the official Oracle RPM: `jdk-21_linux-x64_bin.rpm`.
* The package integrity was successfully validated using the official SHA-256 checksum prior to installation.

## 5. Environment Configuration
The Java environment is fully persistent across sessions.
* **Global configuration:** `/etc/profile.d/java_home.sh`
* **User configuration:** `~/.bashrc` (for user `gustavo`)
* **JAVA_HOME:** `/usr/lib/jvm/jdk-21.0.12.1-oracle-x64`

## 6. Validation Evidence
The runtime was validated in a new shell environment:

```bash
$ java -version
java version "21.0.12.1" 2024-07-16 LTS
Java(TM) SE Runtime Environment (build 21.0.12.1+9-LTS-322)
Java HotSpot(TM) 64-Bit Server VM (build 21.0.12.1+9-LTS-322, mixed mode, sharing)

$ which java
/usr/bin/java

$ readlink -f "$(which java)"
/usr/lib/jvm/jdk-21.0.12.1-oracle-x64/bin/java

$ echo $JAVA_HOME
/usr/lib/jvm/jdk-21.0.12.1-oracle-x64
```
*System state post-installation: SELinux remains Enforcing, firewalld is Active, and Networking is intact.*

## 7. Technical Deviations
During the transition from OpenJDK to Oracle JDK, the `alternatives` system did not automatically re-establish the expected pointer for the `java` binary after OpenJDK's removal.
* **Resolution:** A manual correction of the symlink at `/usr/bin/java` was executed to correctly point to the Oracle JDK 21 binary. This was an implementation occurrence and not an architectural decision. The final state is fully functional.

## 8. Compatibility Context & Current Status
* **Java 21:** Operational
* **ORDS 26.1.1+:** Planned
* **APEX 26.1:** Planned

Java 21 has been provisioned exclusively to support the future ORDS Standalone deployment. No application services or ORDS components are currently active.
