Based on the original work of [maximilianschreiber](https://github.com/maximilianschreiber/spring-todo)

# spring-todo
Simple Todo App with Spring MVC, Hibernate, H2, Flyway DB and Thymeleaf on OpenShift

## H2 Database Console

The [H2 database console](https://medium.com/@harittweets/how-to-connect-to-h2-database-during-development-testing-using-spring-boot-44bbb287570) is enabled by default, just go to http://localhost:8080/h2-console and use the following parameters to connect to the in-memory instance:

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
