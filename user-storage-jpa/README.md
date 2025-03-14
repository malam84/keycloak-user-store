user-storage-jpa: User Storage Provider with JPA
========================================================

Level: Beginner  
Technologies: JPA  
Summary: User Storage Provider with JPA  
Target Product: Red Hat build of Keycloak
Source: <https://github.com/redhat-developer/rhbk-quickstarts>  


What is it?
-----------

This is an example of the User Storage SPI implemented using JPA.  It shows you how you might use these components
to integrate _Red Hat build of Keycloak_ with an existing external custom user database.  The example integrates with a simple relational
database schema that has one user table that stores a username, email, phone number, and password for one particular user.
Using the User Storage SPI this table is mapped to the _Red Hat build of Keycloak_ user metamodel so that it can be consumed by the _Red Hat build of Keycloak_
runtime. Before using this example, you should probably read the User Storage SPI chapter of our server developer guide.


System Requirements
-------------------

You need to have _Red Hat build of Keycloak_ running. It is recommended to use _Red Hat build of Keycloak_ 24 or later.

All you need to build this project is Java 17 (Java SDK 17) or later and Maven 3.6.3 or later.

Build and Deploy the Quickstart
-------------------------------

You must first configure the datasource it uses. 
For that, copy the [conf/quarkus.properties](conf/quarkus.properties) to the `conf` directory of the server distribution.
In this file, you have a named datasource using the same name as the [persistence unit](src/main/resources/META-INF/persistence.xml) from the quickstart. By using the same name,
you make sure the persistence unit will be using the correct datasource.

To build the provider, run the following maven command:

   ````
   mvn -Pextension clean install -DskipTests=true
   ````

To install the provider, copy the target/user-storage-jpa-example.jar JAR file to the `providers` directory of the server distribution.

Finally, start the server as follows:

    kc.[sh|bat] start-dev

Enable the Provider for a Realm
-------------------------------
Login to the _Red Hat build of Keycloak_ Admin Console and got to the User Federation tab.   You should now see your deployed provider in the add-provider list box.
Add the provider, save it.  This will now enable the provider for the 'master' realm.  Because this provider implements the UserRegistrationProvider interface, any new user you create in the
admin console or on the registration pages of _Red Hat build of Keycloak_, will be created in the custom store used by the provider.  If you go
to the Users tab in the Admin Console and create a new user, you'll be able to see the provider in action.

Integration test of the Quickstart
----------------------------------

1. Make sure you have a _Red Hat build of Keycloak_ server running with the installed provider, the `quarkus.properties` file and with an administration user with username `admin` and password `admin` in the `master` realm. Your _Red Hat build of Keycloak_ server should be listening on `http://localhost:8180`. You can archive this by running:

```
./kc.sh start-dev --http-port=8180
```

2. You need to have Chrome browser installed and updated to the latest version. See [README](../../README.md#chrome-driver-version) for additional details.
3. Run `mvn clean install -Pextension`

More Information
----------------
The User Storage SPI and how you can use it is covered in detail in our server developer guide.

