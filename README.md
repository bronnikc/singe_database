Role Name
=========

Role create single instance database on file system with next changed parameters:
```yaml
instance_params:
     - {name: "sga_target", value: "1100MB" }
     - {name: "sga_max_size", value: "1100MB"} 
     - {name: "pga_aggregate_target", value: "200MB"}
     - {name: processes, value: 300}
     - {name: cursor_sharing, value: force}
```
- `ORACLE_BASE` - /u01/app/oracle
- `ORACLE_HOME` - /u01/app/oracle/product/12.2/dbhome
- `FILE_DEST` - /u01/app/oracle/oradata

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
        -  role: oracle.oracle_single_database
           become: yes 
           db_name:  orcl
           oracle_dbhome: dbhome_1
           db_archive_mode: archivelog | no_archivelog
           sys_password: oracle4u

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
