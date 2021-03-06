# Config Server
Config Server for centralized configuration.

Adding a new Configuration:
-----------------------------
 * Create a folder with your application name in `src/main/resources`
 * Add the folder in classpath inside `application.properties` [line 3]
 * Add multiple profiles in using hyphen(-) {applicationName}-{profileName}.properties
 * example app1db and app2 are created in the example.

Configuring client to use mentioned properties:
-----------------------------
 
 * Add this dependency into your pom 
 
 ```code
 <dependency>
            <groupId>org.springframework.cloud</groupId>
            <artifactId>spring-cloud-starter-config</artifactId>
            <version>1.4.1.RELEASE</version>
 </dependency>
 ```
 
 * Create `bootstrap.properties`  in `src\main\resources` and ddd following configurations. Assuming your spring cloud sever is running on localhost:8888
 
 ```code
 server.port=8080
 spring.application.name=applicaitonName
 spring.profiles.active=dev
 spring.cloud.config.uri=localhost:8888
 ```
 * To update the data from the client side add `@RefreshScope` on your bean that is using properties.
 and add actuator dependency

 ```code
 <dependency>
 	<groupId>org.springframework.boot</groupId>
	<artifactId>spring-boot-starter-actuator</artifactId>
 </dependency>
 ```
