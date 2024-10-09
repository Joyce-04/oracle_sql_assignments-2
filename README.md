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
STEP2: SHOWING THE CREATED PLUGGABLE DATABASE
We use a single query to help us to determine whether we successfully created a new pluggable database. The query we use is 
“select pdb_name, status from cdb_pdbs;”

![image](https://github.com/user-attachments/assets/b8d162e6-b98e-4645-9607-8cec88892007)

STEP 3:  OPENING THE CREATED PLUGGABLE DATABASE

We first change the current pluggable databases to the one we want to use by using this query;
“alter pluggable database jo_to_delete_pdb open;”

 ![image](https://github.com/user-attachments/assets/021c021a-f1b5-4199-9e49-22994fe9b2f4)


STEP 4: SAVING STATE FOR THE CREATED PLUGGABLE DATABASE

Using this query we successfully save the state of the pluggable database we want to use.
“alter pluggable database jo_to_delete_pdb save state;”

![image](https://github.com/user-attachments/assets/caf5baa9-0b6e-42ed-bda2-a9850ac39248)


STEP 5:   CLOSE AND CHECK PATH FOR UNPLUGGING THE DATABASE
In order to be able to perform any opearation on our pluggable database we are higly recommended to unplug it before anything else.
That is done by this query: “SELECT directory_name, directory_path FROM dba_directories;”

![image](https://github.com/user-attachments/assets/dbdc0605-5e94-4182-bb02-162d66bb8b1a)

STEP 6: UNPLUGGING THE DATABASE FOR DELETING IT
This is done by this query”
“alter pluggable database jo_to_delete_pdb close immediate;”

![image](https://github.com/user-attachments/assets/441161ca-0f0d-4c71-9b0b-25d46b83a1ad)


STEP 7: DELETE OUR PLUGGABLE DATABASE WITH ALL DATA FILES.
Deleting the pluggable database cannot be complete if we do not also delete it datafile, thus we use this query to remove all of it datafiles.
“drop pluggable database jo_to_delete_pdb including datafiles;”

![image](https://github.com/user-attachments/assets/223cdf58-9f13-4789-aa60-51e921f7e6c8)

Next at this point, we completed all the needed steps for creating and deleting the pluggable database.
Verification step: we check if the deleted pluggable database is not showing up.

![image](https://github.com/user-attachments/assets/034e1dce-f8d8-452f-b6a6-3d9994d0d6e5)





