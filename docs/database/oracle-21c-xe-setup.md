# 🗄️ Oracle Database 21c XE Setup & Validation

## 1. Prerequisites and System Users

The `oracle-database-preinstall-21c` package automatically generated the OS users and groups structure:
* **User:** `oracle`
* **Groups:** `oinstall`, `dba`, `oper`, `backupdba`, `dgdba`, `kmdba`, `racdba`

## 2. Environment Variables (`/home/oracle/.bash_profile`)

```bash
export ORACLE_BASE=/opt/oracle
export ORACLE_HOME=/opt/oracle/product/21c/dbhomeXE
export ORACLE_SID=XE
export PATH=$PATH:$ORACLE_HOME/bin
```

## 3. Validation Evidence
```sql
-- Database and PDB Status
SELECT name, open_mode, cdb FROM v$database;
-- Result: XE | READ WRITE | YES

SELECT name, open_mode FROM v$pdbs;
-- Result: XEPDB1 | READ WRITE
```
