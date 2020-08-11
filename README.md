# oracle
Here is the code required for the oracle installation

Code is for Standalone Oracle ASM Installation with database creation for instant oracle setup
                

 Prerequisite:
 =============
           Cent OS 7.7
           Disk should be created prior to the lib configuration.
           Systems with 2 GB to 16 GB RAM, use swap space equal to RAM.
           Download the grid & Db software and keep it in /home/config/
           
                        - linuxx64_12201_database.zip
                        - linuxx64_12201_grid_home.zip
      
Ansible playbooks:
==================

1.SA_INFRA.yaml
2.standalone_asm.yaml
3.SA_OH_SW_INSTALL.yaml
4.SA_DB_CREATE.yaml

SA_INFRA.yaml:
==============
          
         This playbook uses the roles SA_GRIDINFRA which is used to create the required 
             * Directory structures,
             * Users & groups creation
             * selinux configuration
             * disable the firewall 
             * kernel related settings
             * copying the software from master to target 
             * unzipping the software 
             * removing the zipped software in target
             * copy the asmlib files from source to target and install it.
 
standalone_asm.yaml:
====================
         The playbook includes below tasks
            * Copy the grid response file from master to target and changing the permission
            * Grid Installation
            * Root script execution
            * ASM Instance creation
            * ASM diskgroup creation
         
SA_OH_SW_INSTALL.yaml:
======================
         The playbook includes below tasks
             * Copy the db software from master to target
             * Unzip the file
             * Oracle binary installation
             * Root script execution
 
 SA_DB_CREATE.yaml:
 ==================
          This playbook will create the database using the response file in the location /home/config/*.rsp. 
          
 
 Response file location :  /home/config/
 
 Sample user input: /home/info.ini
 
Note:
 
    Edit the response file based on the requirement.
    User input should be in /tmp/info.ini. Please do changes based on your requirement.
                     
                   

            


         

