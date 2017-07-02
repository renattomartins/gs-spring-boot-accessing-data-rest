# gs-spring-boot-accessing-data-rest
This is a simple repository for future reference about how to build an application with Spring Boot that accesses relational JPA (Java Persistence API) data through a hypermedia-based RESTful front end.

It was based in [Accessing JPA Data with REST](https://spring.io/guides/gs/accessing-data-rest/) tutorial.

### Instructions to run the application
1. Clone this repository
2. So, you must choose **one** of the four alternatives bellow to build and run the application:
    1. Alternative 1: If you prefer to use Gradle, run the command `./gradlew bootRun` on root folder
    2. Alternative 2: Or you can build the JAR file using `./gradlew build` and then running the JAR file<br /> `java -jar build/libs/gs-spring-boot-accessing-data-rest-0.1.0.jar`
    3. Alternative 3: If you prefer to use Maven, run the command `./mvnw spring-boot:run` also on root folder
    4. Alternative 4: Or you can yet build the JAR file using `./mvnw clean package` and then running the JAR file<br /> `java -jar target/gs-spring-boot-accessing-data-rest-0.1.0.jar`
3. After this, the service is up. If you visit http://localhost:8080/ you will get a first glimpse of what this server has to offer.

### Some good requests to do:

You can use any REST client, but look at some examples using `curl`:

- The base endpoint:<br />`curl http://localhost:8080`

- Get all people:<br />`curl http://localhost:8080/people`

- Add a new person:<br />`curl -i -X POST -H "Content-Type:application/json" -d "{  \"firstName\" : \"Frodo\",  \"lastName\" : \"Baggins\" }" http://localhost:8080/people`

- Get a person:<br />`curl http://localhost:8080/people/1`

- The search base endpoint:<br />`curl http://localhost:8080/people/search`

- Search for people by last name:<br />`curl http://localhost:8080/people/search/findByLastName?name=Baggins`

- Edit a person:<br />`curl -X PUT -H "Content-Type:application/json" -d "{ \"firstName\": \"Bilbo\", \"lastName\": \"Baggins\" }" http://localhost:8080/people/1`

- Partially edit a person:<br />`curl -X PATCH -H "Content-Type:application/json" -d "{ \"firstName\": \"Bilbo Jr.\" }" http://localhost:8080/people/1`

- Delete a person:<br />`curl -X DELETE http://localhost:8080/people/1`


### About development environment

- Java 1.8.0_25
- Spring Boot 1.5.2
- Gradle 4.0
- Groovy 2.4.11
- Gradle Wrapper 2.13
- Ant 1.9.6
- Apanche Maven 3.5.0
- POM Model 4.0.0
- Takari Maven Wrapper 0.1.5
- Mac OS 10.12.5 x86_64
- Eclipse IDE Neon 4.6.3
- Atom 1.18.0 x64
- Git 2.8.1
- Tower 2.4.0 for OSx

## Some concepts

**Spring Data REST** - Exports Spring Data repositories as hypermedia-driven RESTful resources. Spring Data REST takes the features of Spring HATEOAS and Spring Data JPA and combines them together automatically. Spring Data REST uses the [HAL format](http://stateless.co/hal_specification.html) for JSON output.

**Spring Data JPA** - Makes it easy to implement JPA-based repositories.

**Spring HATEOAS** - Create REST representations that follow the HATEOAS principle from your Spring-based applications.

**Spring Data Commons** - Core Spring concepts underpinning every Spring Data project.

**HAL format** - HAL (Hypertext Application Language) is a simple format that gives a consistent and easy way to hyperlink between resources in your API.

## Some other details

### Used annotation
- @Entity
- @Id
- @GeneratedValue(strategy = GenerationType.AUTO)
- @RepositoryRestResource(collectionResourceRel = "people", path = "people")
- @Param("name")
- @SpringBootApplication

#### Related annotation
- @Configuration
- @EnableAutoConfiguration
- @EnableWebMvc
- @ComponentScan

#### Annotations used on test case
- @RunWith(SpringRunner.class)
- @SpringBootTest
- @AutoConfigureMockMvc
- @Autowired
- @Before
- @Test
