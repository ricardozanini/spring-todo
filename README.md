Based on the original work of [maximilianschreiber](https://github.com/maximilianschreiber/spring-todo)

# spring-todo
Simple Todo App with Spring MVC, Hibernate, H2, Flyway DB and Thymeleaf on OpenShift

## Running on OpenShift

There are a couple templates available to run. With the peristent ones, you can scale your pods at will or kill them completely and then scale up again. Your data you be kept untouched, persisted and shared between pods.

### Spring Boot on EAP with H2 Persistent Storage

This template will deploy the Todo Application in a JBoss EAP image with a H2 embedded database with a persistent storage:

```shell
git clone https://github.com/ricardozanini/spring-todo.git
cd spring-todo
oc new-project todo
oc create -f openshift/springboot-eap-h2-persistent.yaml
oc new-app springboot-eap-h2-persistent
```

### Spring Boot with H2 Persistent Storage

Deploy the application into a Java Image with Red Hat OpenJDK 1.8. This means no JEE container:

```shell
git clone https://github.com/ricardozanini/spring-todo.git
cd spring-todo
oc new-project todo
oc create -f openshift/springboot-h2-persistent.yaml
oc new-app springboot-h2-persistent
```

## H2 Database Console

The [H2 database console](https://medium.com/@harittweets/how-to-connect-to-h2-database-during-development-testing-using-spring-boot-44bbb287570) is enabled by default (only on non-JEE containers), just go to http://localhost:8080/h2-console and use the following parameters to connect to the in-memory instance:

```
JDBC URL: jdbc:h2:mem:testdb
User Name: sa
Pasword: <leave this empty>
```

When running on OpenShift, change the URL to:

```
JDBC URL: jdbc:h2:/deployments/data/todo
User Name: sa
Pasword: <leave this empty>
```
