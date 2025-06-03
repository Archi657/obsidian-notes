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

logging.level.root=warn
```
## Banner off
spring.main.banner-mode=off
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
# Hibernate/JPA
Hibernate: Framework for persisting/saving Java objects in a DB
- Hadles all of the low level SQL
- MInimizes the quantity of JDBC code
- ORM
JPA Standard API using Hibernate implementation or any from other vendor.

### Entity Class
@Entity class : Java class mapped to a db table. Must have public-protected constructor no arguments
``` Java
@Entity
@Table(name="Student")
public class Student{
	@Id
	@Column(name=id) //optional
	private int id;
}

```
### Entity Value
 @GeneratedValue (stratedy=)
 https://stackoverflow.com/questions/47676403/spring-generatedvalue-annotation-usage
 **GenerationType.AUTO** : Default and let's persistance to choose, for example hibernate will use a strategy depending the db, in almost every it will use **GenerationType.SEQUENCE***.
**GenerationType.IDENTITY** : Auto-increment.
**GenerationType.SEQUENCE**  : You gotta provide a sequence.
**GenerationType.TABLE**  : Rarely used.

### DAO Data Access Object
Implements methods and talks to the db. It will talk to the data entity manager, this one needs a data source which is the db connection info.
