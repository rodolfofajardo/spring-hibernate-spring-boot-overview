# Spring Boot and Hibernate Udemy Training
## 1 Spring Boot Overview

### First Commit: Spring Boot Overview
Spring Projects:
https://spring.io/projects

Spring Boot Initializr:
https://start.spring.io/

Full list of Spring Boot Starters:
https://docs.spring.io/spring-boot/docs/current/reference/htmlsingle/#using.build-systems.starters

### Second Commit: Spring Boot Devtools
Automatically restarts your application when code is updated
1. Add spring-boot-devtools dependency
2. Select: Preferences > Build, Execution, Deployment > Compiler
and check box Build project automatically
   (IntelliJ CE)
3. Select: Preferences > Advanced Settings
   Check box: Allow auto-make to ...
   (IntelliJ CE)

More on Developer Tools:
https://docs.spring.io/spring-boot/docs/current/reference/htmlsingle/#using.devtools

### Third Commit: Spring Boot Actuator
In order to make use of Actuator, add
spring-boot-starter-actuator to pom

This will expose /actuator/health by default

To expose /info endpoint, add to
application.properties file:
```
management.endpoints.web.exposure.include=health,info
management.info.env.enabled=true
```

/info endpoint is for custom properties,
in order to publish them, add to
application.properties file
(info prefix is mandatory):
```
info.app.name=My Super Cool App
info.app.description=Demo application for Spring Boot
info.app.version=1.0.0
```
To expose all actuator endpoints:
```
management.endpoints.web.exposure.include=*
```
Full list of actuator endpoints:
https://docs.spring.io/spring-boot/docs/current/reference/htmlsingle/#actuator.endpoints

### Fourth Commit: Spring Boot Actuator Security
Add spring-boot-starter-security to pom
and all endpoints are secured,
except for /health.

When accessing an endpoint, a sign in
dialog will appear. Default user is 
'user', and the password is shown in
the console.

To customize user and password,
add the following lines to
application.properties file:

```
spring.security.user.name=myuser
spring.security.user.password=mypassword
```
To exclude /health and /info
```
management.endpoints.web.exposure.exclude=health,info
```
More on Spring Boot Actuator:
https://docs.spring.io/spring-boot/docs/current/reference/htmlsingle/#actuator

## Fifth Commit: Command Line Execution
There are two options to run a Spring
Boot Application:
```
$ java -jar mycoolapp.jar
```
```
$ ./mvnw package
$ ./mvnw spring-boot:run
```
