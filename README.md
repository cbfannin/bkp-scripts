**SET UP**<br/>
1. Make a copy of the bkp-script.sh file and place it in to the mybkps directory with a name that relfects your project.
`cp bkp-script.sh mybkps/myproject.sh`
1. Change in to the mybkps directory.
`cd mybkps`
1. Edit the newly copied script file adding all the required variables.
1. Source the script or start a new terminal so the script will be recognized.
`source ./myproject.sh`

**RUN**<br/>
While in your mybkps directory Run
`./myproject`

**IMPORT**<br/>
If all worked according to plan, you should now have the most recent database and files backup in your project's root directory on your local machine. From your project's root directory, you just need to:
1. Import the database.
`lando db-import <database-name>`
1. Extract the files. Be sure to replace "filesbkp.tar.gz" with the name of the file backup name you retreived from the remote server.
`tar -xvf filesbkp.tar.gz -C /web/sites/default/`
1. Clear Cache.
`drush cache rebuild`

**CLEANUP**<br/>
At this point it is OK to remove the downloaded backups. You may keep them incase you bork your local and need to reimport them. Just repeat the IMPORT steps above. If you wish to get rid of the files you can do so by `rm database-bkp-name.tar.gz && rm files-bkp-name.tar.gz`. Again replace the filenames with the actual filenames you retrieved from the remote server.
