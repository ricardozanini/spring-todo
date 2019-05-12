Based on the original work of [maximilianschreiber](https://github.com/maximilianschreiber/spring-todo)

# spring-todo
Simple Todo App with Spring MVC, Hibernate, H2, Flyway DB and Thymeleaf on OpenShift

## H2 Database Console

The H2 database console is enabled by default, just go to http://localhost:8080/h2-database and use the following parameters to connect to the in-memory instance:

```
JDBC URL: jdbc:h2:mem:testdb
User Name: sa
Pasword: <leave this empty>
```

When running on OpenShift using the persistent template, change the URL to:

```
JDBC URL: jdbc:h2:/opt/eap/data/todo
User Name: sa
Pasword: <leave this empty>
```
