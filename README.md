Howto setup de.indymedia.org drupal page
========================================

Step by step howto for a drupal based indymedia page used by the german imc.

1) Download drupal 7.x and install it somewhere, like /var/www/drupal (later called <installdir>)
  
2) Init database: https://drupal.org/documentation/install/create-database

3) Adjust <installdir>/site/default/settings.php

4) Now prepare the look and feel: Download the stylesheet using git. 

      cd <installdir>/site/all/themes
      git clone https://github.com/SchoScho/de.indymedia.org.drupal.css.git

5) Start apache and mysql (if not already running) 

6) Now open the installed page in your browser. The install.php will start. Select the minimal profile!

7) Download and enable the following modules using drush (apt-get install drush)

    cd <installdir>
    drush dl backup_migrate creative_commons ctools date editablefields entity features features_extra field_permissions file_entity flag indymedia_cities rules session_api submitted_by token views views_rules 
    drush en backup_migrate creative_commons ctools date editablefields entity features features_extra field_permissions file_entity flag indymedia_cities rules session_api submitted_by token views views_rules 

Alternatively you can login into the new page and install these modules manually - file by file. 
    
7) Now download the features using git. At these features all the needed de.indymedia.org functionality is included. Maybe using the /tmp directory: 

    cd /tmp
    git clone https://github.com/SchoScho/features.git

8) Login into your new page and select structure->features and install all modules from step 7: Select one tar file after another from /tmp/feature/)

9) Select under Appearance the lime css

10) Create Moderator, Admin and Super admin roles and set permissions as you like

11) Grant permissions (moderators, admins or super admins) to the members of your imc

