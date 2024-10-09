# oracle_sql_assignments-2


DELETING A PDB
Creating another pluggable database and later we will delete it.
This documentation covers more information on how to create a pluggable database and other steps involved in changing instances, unplugging created pluggable devices, deleting pluggable databases, and many others as everything will be shown by their successful screenshots. 
Step 1:  We first create a new pluggable database by typing:

“create pluggable database jo_to_delete_pdb
admin user jo_plsqlauca identified by Batete
file_name_convert =('C:\ORACLE21C\ORADATA\ORCL\pdbseed\',
  4  'C:\ORACLE21C\ORADATA\ORCL\ORCLPDB\jo_to_delete_pdb\');”

  ![image](https://github.com/user-attachments/assets/6c37ccab-ceda-4bc7-aa88-2bab2e76b5a3)
