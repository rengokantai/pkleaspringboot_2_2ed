# pkleaspringboot_2_2ed
## Quick Start With Java
### Getting started
Some annotations:
- @SpringBootApplication annotation tells Spring Boot, when launched, to scan recursively for Spring components inside this package and 
register them. It also tells Spring Boot to enable autoconfiguraion, a process where beans are automatically created based on classpath settings,
property settings, and other factors.



Sample REST controller:
- The @RestController anotation indicates that we dont want to render views, but write the results straight into the response body instead.
- @Getmapping is shorthand of @RequestMapping(merhod=RequestMethod.GET)



Simple MongoDB pojo
- @Data annotation. generate getter setter toString equals hashCode constructor
- @Document: suitable for mongoDB data store
- @Id: primary key


ReactiveCrudRepository
- ReactiveCrudRepository extends Repository.
```
public interface CRepo extends ReactiveCrudRepository<Chapter,String>{}
```


Preload the database
```
import reactor.core.publisher.Flux;
```
note
- @Configuration marks this class as a source of beans
- @Bean indicates that the return value of init() is a Spring Bean




### Bundling up the application as a runnable JAR file
```
./gradlew clean build
SERVER_PORT=8000 java -jar build/libs/learning-spring-boot-0.0.1-SNAPSHOT.jar
```

### Deploying to Cloud Foundry
```
cf push appname -p build/libs/appname.jar
```


### Metrics
```
endpoints.metrics.enabled=true
```

