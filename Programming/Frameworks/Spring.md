## Run from terminal
``` Bash
mvnw package
java -jar target/file.jar
# with maven plugin
mvnw spring-boot:run
```
## Use properties
``` Bash
# application.properties
teacher.name=juan
# code
@Value("${teacher.name}")
private String teachersName;
```
## Logging level
``` Bash
logging.level.org.springframework=DEBUG
logging.level.org.hibernate=TRACE

logging.file.name=logname.log
logging.file.path=c:/path
```
## Web properties
``` Bash
server.port=7070

```
## Qualifier when you have many beans
![[Pasted image 20250420152004.png]]
## Lazzy initialization
``` Bash
spring.main.lazy-initiialization=true
```
## Bean Scope
Singleton = Single shared instance of the bean
Prototype = New bean for each container request
Only for web apps ->
Request = Scoped to an HTTP web request 
Session = Scoped to an HTTP web session
Application = Scoped to a web app ServletContext
Websocket
``` Java
@Scope(ConfigurableBeanFactory.SCOPE_SINGLETON)
```