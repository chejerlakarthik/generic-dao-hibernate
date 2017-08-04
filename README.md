### How to start

* Please use `Maven2` basically

```
$ git clone 
$ cd generic-dao-hibernate
$ mvn package
$ mvn jetty:run
```

* Database Initialization

from console

```
mysql> create database sample character set utf8;
```

from maven

```
$ mvn flyway:info -Dflyway.configFile=flyway.properties
$ mvn flyway:migrate -Dflyway.configFile=flyway.properties
```

* Temporary app server
```
$ sh -c "mvn jetty:run &"
```

* Please find API documents page at http://localhost:8080/

### Software information

* **Jersey** for REST API application server

    * See, https://jersey.java.net/release-notes/2.23.2.html
    * Using version 2.23.2 **(see pom.xml also)**

* **Hibernate** for O/R Mapping

    * Using version 5.2.4.Final **(see pom.xml also)**

* **Spring4** for DI

    * Using version 4.3.3.RELEASE **(see pom.xml also)**

* **Lombok** for generating Getter/Setter

    * Using version higher than 1.16.x **(see pom.xml also)**

* **Swagger** for generating documents

    * Using version 1.5.10

* **Swagger-UI** to see pretty documents as HTML

    * See, https://github.com/swagger-api/swagger-ui/releases/tag/v2.2.6
    * Using version 2.2.6

### Deploy it to Heroku (just for reference)

* First time only
* Also, you need to install `heroku-toolbelt`

```
$ heroku apps:create [:your-app-name:]
$ heroku plugins:install https://github.com/heroku/heroku-deploy
$ heroku deploy:war --war target/[:your-war-name:].war --app [:your-app-name:]
```
