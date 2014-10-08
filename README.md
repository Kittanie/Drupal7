Drupal7
=======

#Drupal Apache Solr Search Module

Read Me for installation and configuartion of Apache Solr Search Module wiithin a Drupal website. 

This will require a drupal website already been setup and being hosted either locally or on a webserver.

My Path: "C:\Users\ivyd\Documents\My Web Sites\drupaltest"

Hosting: localhost:62339/drupal/

Drupal 7 - (https://www.drupal.org/) 

Check what version of Java is installed - "Java -version" in cmd. If its lower than 1.7 install the lastest Java Update.

Solr Server Tutorial - (http://webwash.net/tutorials/how-setup-local-solr-server-search-api)


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
4. Copy solrconfig.xml & schema.xml from (drupal\sites\all\modules\search_api_solr\solr-conf\3.x) into (solr\drupal-solr\solr)
5. Open CMD and navigate to your "drupal-solr" folder.
6. Run the command "java -jar start.jar".
7. In the browser go to (localhost:8983/solr) you should see the solr admin page. 
8. Go to Drupal - Configuration, Apache Solr Search, Settings & click the default server. 
9. Set the Solr Server URL to "http://localhost:8983/solr" - Save & Edit.
10. Click Test Connection and you should see the message: "Your site has contacted the Apache Solr server.".

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

1. Search Settings - Apache Solr Search Module & Default checked. 
2. Index the site.
3. Apache Solr Search - Select all for configuration, Set page/blocks & attachments. 
4. Settings - localhost server "default" (http://localhost:8983/solr) - This will be the search enirvoment for all indexed content. Content must be indexed to the solr server for it to work. 
5. Default Index - Index all queued content. 

## Apache Solr Search Within Files 
This tutorial will explain to how to give Apache Solr Search the ability to search within .pdf files and extract the content out and be shown within our search results. 

### Maven 

1. Make sure to have the latest Java JDK installed (http://www.oracle.com/technetwork/java/javase/downloads/index.html)
2. Set the Java JDK in your JAVA_HOME e.g. "C:\Program Files\Java\jdk1.8.0_20" enviroment varible in system varibles & add to path.  
3. Download Maven (http://maven.apache.org/download.cgi)
4. Set M2_HOME enviroment system varible e.g. "C:\Program Files\apache-maven-3.2.3"
5. Set M2 system variable = %M2_HOME%/bin
6. Set MAVEN_OPTS system variable = -Xms256m -Xmx512m (This will allocate the amount of memory we will have for out maven build)
7. Make sure to declare these variables within the path system variable. 



 






