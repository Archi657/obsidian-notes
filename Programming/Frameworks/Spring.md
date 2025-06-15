## Run from terminal
``` Bash
mvnw package
java -jar target/file.jar
# with maven plugin
mvnw spring-boot:run
```
# Application.properties

``` Bash
# application.properties
teacher.name=juan
# code
@Value("${teacher.name}")
private String teachersName;

#change port
server.port=7070
```
## Logging level
``` Bash
logging.level.org.springframework=DEBUG
logging.level.org.hibernate=TRACE
# sql statements
logging.level.org.hibernate.SQL=debug
logging.level.org.hibernate.orm.jdbc.bind=trace 

logging.file.name=logname.log
logging.file.path=c:/path

logging.level.root=warn
# banner off
spring.main.banner-mode=off
```

# Beans
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
![[Pasted image 20250610202848.png]]
`spring.jpa.hibernate.ddl-auto=create`

Hibernate: Framework for persisting/saving Java objects in a DB
- Hadles all of the low level SQL
- MInimizes the quantity of JDBC code
- ORM
JPA Standard API using Hibernate implementation or any from other vendor.

Entity manager low level, work directly with JPA allowing complex queries meanwhile JPA Repository is more abstract. Has @Query and paging and sorting. Both can be used.

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
 @GeneratedValue (strategy=)
 https://stackoverflow.com/questions/47676403/spring-generatedvalue-annotation-usage
 **GenerationType.AUTO** : Default and let's persistance to choose, for example hibernate will use a strategy depending the db, in almost every it will use **GenerationType.SEQUENCE***.
**GenerationType.IDENTITY** : Auto-increment.
**GenerationType.SEQUENCE**  : You gotta provide a sequence.
**GenerationType.TABLE**  : Rarely used.

### DAO Data Access Object
@Repository 
Implements methods and talks to the db. It will talk to the data entity manager, this one needs a data source which is the db connection info.

First we add an interface and then we implement it.
### Create-Save-Findall
##### main program
```Java
@Bean  
public CommandLineRunner commandLineRunner(StudentDAO studentDAO){  
    return runner -> {   
       readStudent(studentDAO);
       createStudent(studentDAO); 
       queryForStudents(studentDAO)
    };  
}  

  private void readStudent(StudentDAO studentDAO) {  
    int id=2;  
    Student myStudent = studentDAO.findById(id);  
    System.out.println(myStudent);  
}

private void createStudent(StudentDAO studentDAO) {  
    Student student = new Student("Juan", "Perez", "hisemail.com");  
    studentDAO.save(student);  
    System.out.println("Student generated " + student.getId());  
}

public void queryForStudents(StudentDAO studentDAO){
	List<Student> students = studentDAO.find(all);

	for(Student student: students){
		sout(student);
	}
}

private void readStudent(StudentDAO studentDAO) {  
    int id=2;  
    Student myStudent = studentDAO.findById(id);  
    System.out.println(myStudent.getId());  
}
```
##### Student
```Java
import jakarta.persistence.*;  
  
@Entity  
@Table(name = "student")  
public class Student {  
    @Id  
    @GeneratedValue(strategy = GenerationType.IDENTITY)  
    @Column(name = "id")  
    private int id;  
	.
	.
    public Student() {  
  
    }  
  
    public Student( String firstName, ...) {  
        this.firstName = firstName;  
        ...
    }  
}
```

##### StudentDAO
```Java
public interface StudentDAO {  
  
    void save(Student student);
    Student findById(Integer id);
	List<Student> findAll();
}
```
##### StudentDAOImpl
```Java
import jakarta.persistence.EntityManager;  
import org.springframework.beans.factory.annotation.Autowired;  
import org.springframework.stereotype.Repository;  
import org.springframework.transaction.annotation.Transactional;  
  
@Repository  
public class StudentDAOImpl implements StudentDAO{  
  
    private EntityManager entityManager;  
  
    @Autowired // optional if only 1 constructor  
    public StudentDAOImpl(EntityManager entityManager) {  
        this.entityManager = entityManager;  
    }  
  
    @Override  
    @Transactional    public void save(Student student) {  
        entityManager.persist(student);  
    }  

	@Override  
	public Student findById(Integer id){  
	    return entityManager.find(Student.class, id);  
	}

	@Override
	public List<Student> findAll(){
		TypedQuery<Student> theQuery = entityManager.createQuery("FROM Student", Student.class);

		return theQuery.getResultList();
	}
	@Override  
	public Student findById(Integer id){  
	    return entityManager.find(Student.class, id);  
	}
}
```
### Update entity
```Java
// method in DAO interface
void update(Student student);

// DAO impl
@Override
@Transactional
public void update(Student student){
	entityManager.merge(student);
}

// main
updateStudent(studentDAO);

private void updateStudent(StudentDAO studentDAO){
	int studentId= 1;
	Student student = studentDAO.findbyId(studentId);
	student.setFirstNAme("meow");
	studentDA.update(student);
}

```
### Delete entity
```Java
//DAO inter
void delete(Integer id);

//DAO impl
@Override
@Transactional
public void delete(Integer id){
	Student student = entityManager.find(Student.class, id);
	entityManager.remove(student);
}

//main
deleteStudent(studentDAO);

private void deleteStudent(StudentDAO studentDAO){
	int studentId = 3 ;
	studentDAO.delete(studentId);
}

```
### JPQL
Syntax is based on entity names and values, not the db.

```Java
TypedQuery<Student> theQuery = entityManager.createQuery("FROM Student order by lastName", Student.class);

"FROM student where column=:theData"
theQuery.setParameter("theData", variable);

"DELETE FROM Student" // delete all

```
## REST CRUD APIs
Required dependency
``` Bash
# pom.xml
<dependency>
	<groupId>org.springframework.boot</groupId>
	<artifactId>spring-boot-starter-web</artifactId>
<dependency/>
```
##### Data binding/Serialization/Marshalling
Java JSON Data BInding is converting a JSON into a Java POJO, or the other way around. 

Jackson is a project that handles the data binding and spring uses in the background.

##### RestController
``` Java
@RestoController
@RequestMapping("/test")
public class DemoRestController{
	return "hi";
}
```
