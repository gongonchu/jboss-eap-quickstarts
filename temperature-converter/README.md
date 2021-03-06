temperature-converter: Stateless Session EJB (SLSB)
=================================================
Author: Bruce Wolfe  
Level: Beginner  
Technologies: CDI, JSF, SLSB EJB  
Summary: The `temperature-converter` quickstart does temperature conversion using an *EJB Stateless Session Bean* (SLSB), *CDI*, and a *JSF* front-end client.   
Target Product: JBoss EAP  
Source: <https://github.com/jboss-developer/jboss-eap-quickstarts/>  

What is it?
-----------

The `temperature-converter` example demonstrates the use of an *EJB Stateless Session Bean* (SLSB) and *CDI*, accessed using a *JSF*, and deployed to Red Hat JBoss Enterprise Application Platform using a WAR archive.

The application does the following:

1. The User Interface is a JSF page that asks for a temperature and a scale (Fahrenheit or Celsius).
2. When you click on `Convert`, the temperature string is passed to the TemperatureConverter controller (managed) bean.
3. The managed bean then invokes the `convert()` method of the injected TemperatureConvertEJB (notice the field annotated with @Inject).
4. The response from TemperatureConvertEJB is stored in the `temperature` field of the managed bean.
5. The managed bean is annotated as @SessionScoped, so the same managed bean instance is used for the entire session.


System requirements
-------------------

The application this project produces is designed to be run on Red Hat JBoss Enterprise Application Platform 7 or later. 

All you need to build this project is Java 8.0 (Java SDK 1.8) or later, Maven 3.0 or later.

 
Configure Maven
---------------

If you have not yet done so, you must [Configure Maven](https://github.com/jboss-developer/jboss-developer-shared-resources/blob/master/guides/CONFIGURE_MAVEN.md#configure-maven-to-build-and-deploy-the-quickstarts) before testing the quickstarts.


Use of EAP_HOME
---------------

In the following instructions, replace `EAP_HOME` with the actual path to your JBoss EAP installation. The installation path is described in detail here: [Use of EAP_HOME and JBOSS_HOME Variables](https://github.com/jboss-developer/jboss-developer-shared-resources/blob/master/guides/USE_OF_EAP_HOME.md#use-of-eap_home-and-jboss_home-variables).


Start the JBoss EAP Server
-------------------------

1. Open a command prompt and navigate to the root of the JBoss EAP directory.
2. The following shows the command line to start the server:

        For Linux:   EAP_HOME/bin/standalone.sh
        For Windows: EAP_HOME\bin\standalone.bat


Build and Deploy the Quickstart
-------------------------

_NOTE: The following build command assumes you have configured your Maven user settings. If you have not, you must include Maven setting arguments on the command line. See [Build and Deploy the Quickstarts](https://github.com/jboss-developer/jboss-developer-shared-resources/blob/master/guides/BUILD_AND_DEPLOY.md#build-and-deploy-the-quickstarts) for complete instructions and additional options._

1. Make sure you have started the JBoss EAP server as described above.
2. Open a command prompt and navigate to the root directory of this quickstart.
3. Type this command to build and deploy the archive:

        mvn clean install jboss-as:deploy

4. This will deploy `target/jboss-temperature-converter.war` to the running instance of the server.
 

Access the application 
---------------------

The application will be running at the following URL: <http://localhost:8080/jboss-temperature-converter/>.

You will be presented with a simple form for temperature conversion.

1. Optionally, Select a scale: Celsius or Fahrenheit.
2. Enter a temperature.
3. Press the `Convert` button to see the results.


Undeploy the Archive
--------------------

1. Make sure you have started the JBoss EAP server as described above.
2. Open a command prompt and navigate to the root directory of this quickstart.
3. When you are finished testing, type this command to undeploy the archive:

        mvn jboss-as:undeploy


        
Run the Quickstart in Red Hat JBoss Developer Studio or Eclipse
-------------------------------------
You can also start the server and deploy the quickstarts or run the Arquillian tests from Eclipse using JBoss tools. For general information about how to import a quickstart, add a JBoss EAP server, and build and deploy a quickstart, see [Use JBoss Developer Studio or Eclipse to Run the Quickstarts](https://github.com/jboss-developer/jboss-developer-shared-resources/blob/master/guides/USE_JBDS.md#use-jboss-developer-studio-or-eclipse-to-run-the-quickstarts) 


Debug the Application
------------------------------------

If you want to debug the source code of any library in the project, run the following command to pull the source into your local repository. The IDE should then detect it.

      mvn dependency:sources
     


