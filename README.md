Drupal7
=======

#Drupal Apache Solr Search Module

Read Me for installation and configuartion of Apache Solr Search Module wiithin a Drupal website. 

This will require a drupal website already been setup and being hosted either locally or on a webserver.

My Path: "C:\Users\ivyd\Documents\My Web Sites\drupaltest"

Hosting: localhost:62339/drupal/

Drupal 7 - (https://www.drupal.org/) 

Check what version of Java is installed - "Java -version" in cmd. If its lower than 1.7 install the lastest Java Update.


##Installation

Installation instructions on both the apache solr dupal search module and the solr server which it connects to. 


### Apache Solr Search Module

1. Download apachesolr-7.x-1.7.zip at (https://www.drupal.org/project/apachesolr).
2. Make a contrib folder in the "yoursite\drupal\sites\all\modules" directory.
3. Extract the apachesolr.zip into the "yoursite\drupal\sites\all\modules\contrib" directory.
4. Go to your drupal site in your browser signed in as admin.
5. Go to modules, the Apache Solr module will be at the bottom of the page.
6. Enable the checkboxes and click save configuration. 

	* This message may appear: Apache Solr is enabled. Visit the settings page.
	The configuration options have been saved.

	Warning message
	Your content must be re-indexed before Apache Solr Access will be functional on searches.
	No update information available. Run cron or check manually.

7. Click check manually

	*Regularly review and install available updates to maintain a secure and current site. Always run the update script each time a module is updated.

OR 

8. (Optional) go into configuration, cron and click run cron. Both of these options will re-index the site to make apache solr functional. 

### Apache Solr Server

1. Download solr-4.10.0.zip from a mirror (http://lucene.apache.org/solr/)
2. Extract the zip into your website folder - So mine would be "C:\Users\ivyd\Documents\My Web Sites\drupaltest\solr".
3. Duplicate example folder and give a relevant name e.g. "drupal-solr".
4. Open CMD and navigate to your "drupal-solr" folder.
5. Run the command "java -jar start.jar".
6. In the browser go to (localhost:8983/solr) you should see the solr admin page. 
7. Go to Drupal - Configuration, Apache Solr Search, Settings & click the default server. 
8. Set the Solr Server URL to "http://localhost:8983/solr" - Save & Edit.
9. Click Test Connection and you should see the message: "Your site has contacted the Apache Solr server.".

### Create Search API Server

1. Download search_api_solr-7.x-1.4.tar.gz form (https://www.drupal.org/node/1254698)
2. Go Modules & Install new modules.
3. Upload the search_api_solr file.
4. Once installed, enable the module & save configuration - run cron or check manually. 

	* Other Modules that may be needed:
		- Search_Api (https://www.drupal.org/project/search_api)
		- Entity (https://www.drupal.org/project/entity)
		- Views (https://www.drupal.org/project/views)
		- CTools (https://www.drupal.org/project/CTools)

5. Go configuration, Search API and Add server. 
6. Server Name "solr server" and chose solr service from the Service Class dropdown - Create Server

### Private File Permissions (ISS Server Only)

1. Download the Node View Permissions Module (https://www.drupal.org/project/node_view_permissions)
2. Enable, Update & Cron. 

### ApacheSolr Configuration

1. 

