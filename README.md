Role Name
=========

Role create single instance database on file system with next changed parameters:

This parameters can be changed at vars/main.yml
```yaml
instance_params:
     - {name: "sga_target", value: "1100MB" }
     - {name: "sga_max_size", value: "1100MB"} 
     - {name: "pga_aggregate_target", value: "200MB"}
     - {name: processes, value: 300}
     - {name: cursor_sharing, value: true}
```
- `ORACLE_BASE` - /u01/app/oracle
- `ORACLE_HOME` - /u01/app/oracle/product/12.2/dbhome
- `FILE_DEST` - /u01/app/oracle/oradata

Requirements
------------

Before run this role, you must install ORACLE SOFTWARE 12.2 using next role:

https://git.apps.okd.dcteam.local/oracle-ansible/install_oracle_home

Role Variables
--------------
- `db_name` - database unque name
-  `oracle_dhome` - database home from which to run dbca
- `db_archive_mode` - database archive mode: archivelog or no_archivelog
- `sys_password` - password for all database users

 #### **Password for administrative accounts**
```yml
sys_password: SysPassDcteam2020
```
 


Dependencies
------------



Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
        -  role: oracle.oracle_single_database
           become: yes 
           db_name:  orcl
           oracle_dbhome: dbhome_1
           db_archive_mode: archivelog
           sys_password: oracle4u

