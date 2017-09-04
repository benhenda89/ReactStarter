## MarketPlace Spring Boot React Starter

This Maven project is meant to be used as a solid starter project for any [Broadleaf Commerce](http://www.broadleafcommerce.org) application.
It has many sensible defaults set up along with examples of how a fully functioning eCommerce site based on Broadleaf might work. 

## Running the applications
This starter contains several runnable applications: `site`, `admin`, and `api`.
You can run `admin` and `api` as any other Spring Boot application (http://docs.spring.io/spring-boot/docs/current/reference/html/using-boot-running-your-application.html)
These applications automatically configure and start an HSQL DB and SOLR instance (if not already configured).
By default, these will be located in your `java.io.tmp` directory.

### Running the `site` application

The `site` application is a runnable NodeJS application. You will need to be sure to be running the `api` application first,
as the `site` application is not functional without the `api`. The startup documentation for running the `site` 
application can be found [here](./site/docs/React-Starter-Startup.md).

### Run using the Maven plugin (Recommended)
You can run any of the applications in an exploded form using the Spring Boot Maven Plugin:

##### Running Admin:
```
   > cd admin
   > mvn spring-boot:run
```
> Note: Default debug port open on `8084` 

##### Running API:
```
   > cd api
   > mvn spring-boot:run
```
> Note: Default debug port open on `8085` 

### Running as a packaged application
You can also run any of the applications as an executable jar:

##### Running Admin:

```
   > cd admin
   > java -Xmx1536M -Xdebug -Xrunjdwp:transport=dt_socket,address=8084,server=y,suspend=n -javaagent:target/agents/spring-instrument.jar -jar ./target/boot-starter-admin-5.2.0-GA.jar
```

##### Running API:

```
   > cd api
   > java -Xmx1536M -Xdebug -Xrunjdwp:transport=dt_socket,address=8085,server=y,suspend=n -javaagent:target/agents/spring-instrument.jar -jar ./target/boot-starter-api-5.2.0-GA.jar
```
