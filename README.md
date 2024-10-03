## commands to create and delete a pluggable database

Microsoft Windows [Version 10.0.22631.4169]
(c) Microsoft Corporation. All rights reserved.

C:\Users\HP>sqlplus / as sysdba

SQL*Plus: Release 21.0.0.0.0 - Production on Thu Oct 3 14:09:43 2024
Version 21.3.0.0.0

Copyright (c) 1982, 2021, Oracle.  All rights reserved.


Connected to:
Oracle Database 21c Enterprise Edition Release 21.0.0.0.0 - Production
Version 21.3.0.0.0

SQL> exit
Disconnected from Oracle Database 21c Enterprise Edition Release 21.0.0.0.0 - Production
Version 21.3.0.0.0

C:\Users\HP>sqlplus/ as sysdba

SQL*Plus: Release 21.0.0.0.0 - Production on Thu Oct 3 14:20:56 2024
Version 21.3.0.0.0

Copyright (c) 1982, 2021, Oracle.  All rights reserved.


Connected to:
Oracle Database 21c Enterprise Edition Release 21.0.0.0.0 - Production
Version 21.3.0.0.0

SQL> create pluggable database plsql_class2024db
  2  admin user pdbadmin identified by admin
  3  file_name_convert=('D:\restricted\oracle21c\oradata\ORCL\pdbseed\','D:\restricted\oracle21c\oradata\ORCL\plsql_class2024db\');

Pluggable database created.

SQL> alter session set container= plsql_class2024db;

Session altered.

SQL> alter pluggable database plsql_class2024db open;

Pluggable database altered.

SQL> alter pluggable database plsql_class2024db save state;

Pluggable database altered.

SQL> create user ez_plsqlauca identified by ezra;

User created.

SQL> grant all privileges to ez_plsqlauca;

Grant succeeded.

SQL> alter session set container= cdb$root;

Session altered.

SQL> create pluggable database ez_to_delete_pdb
  2  from orclpdb
  3  file_name_convert=('D:\restricted\oracle21c\oradata\ORCL\orclpdb\','D:\restricted\oracle21c\oradata\ORCL\ez_to_delete_pdb\'
);

Pluggable database created.

SQL> alter pluggable database ez_to_delete_pdb unplug into 'D:\restricted\oracle21c\admin\orcl\dpdump\ez_to_delete_pdb.xml';

Pluggable database altered.

SQL> drop pluggable database ez_to_delete_pdb;

Pluggable database dropped.


## task1: creating a new pluggable database

![Screenshot 2024-10-03 212114](https://github.com/user-attachments/assets/9d991e51-215c-41e9-8dde-f13e91c7abfd)

## task2: creating and deleting a pluggable database

![Screenshot 2024-10-03 213111](https://github.com/user-attachments/assets/2b2379a1-4d8b-482c-8c48-61d3a8ef781f)


## task3: Configure Oracle Enterprise Manager


![Screenshot 2024-10-03 213422](https://github.com/user-attachments/assets/82deae0c-2c89-49c7-a489-edb9ee6bb039)



