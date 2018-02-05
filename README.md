# Config Server
Config Server for centralized configuration.

Adding a new Configuration:
-----------------------------
 * Create a folder with your application name in `src/main/resources`
 * Add the folder in classpath inside `application.properties` [line 3]
 * Add multiple profiles in using hyphen(-) {applicationName}-{profileName}.properties

Configuring client to use mentioned properties:
-----------------------------
 * 