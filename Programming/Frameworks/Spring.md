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
