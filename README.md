bahmni-module-example
==========================

A demonstration module for Bahmni developers

Description
-----------
This is a very basic module which can be used as a starting point in creating a new module.

Building from Source
--------------------
You will need to have Java 8+ and Maven 2.x+ installed.  Use the command 'mvn package' to 
compile and package the module.  The .omod file will be in the omod/target folder.

Alternatively you can add the snippet provided in the [Creating Modules](https://wiki.openmrs.org/x/cAEr) page to your 
omod/pom.xml and use the mvn command:

    mvn package -P deploy-web -D deploy.path="../../openmrs-1.8.x/webapp/src/main/webapp"

It will allow you to deploy any changes to your web 
resources such as jsp or js files without re-installing the module. The deploy path says 
where OpenMRS is deployed.

Installation
------------
1. Build the module to produce the .omod file.
2. Use the OpenMRS Administration > Manage Modules screen to upload and install the .omod file.

If uploads are not allowed from the web (changable via a runtime property), you can drop the omod
into the ~/.OpenMRS/modules folder.  (Where ~/.OpenMRS is assumed to be the Application 
Data Directory that the running openmrs is currently using.)  After putting the file in there 
simply restart OpenMRS/tomcat and the module will be loaded and started.


Dependencies
-----------------
There is a jar file "openerp-java-api-1.5.0.jar" in the common-lib directory. 
The project is hosted on https://sourceforge.net/projects/openerpjavaapi/   

We need to add this jar as a maven dependency.
To do this run the following command.

mvn install:install-file \
   -Dfile=/Users/angshus/bahmni-module-example/common-lib/openerp-java-api-1.5.0.jar \
   -DgroupId=com.debortoliwines.openerp.api \
   -DartifactId=openerp-adapter \
   -Dversion=1.0 \
   -Dpackaging=jar \
   -DgeneratePom=true
