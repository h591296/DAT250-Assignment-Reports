# Experiment 1: JPA tutorial

### Following the JPA tutorial
1. The class ****Main**** ran and terminated without errors.
2. The package relationshipexample was successfully created under no.hvl.dat250.jpa.tutorial
3. The three classes Family, Job, and Person was successfully added to the new package I just made.

To answer the question: “Can you find out which database is used and where the database stores its files?”

The persistence.xml file in src/main/resources/META-INF is used in Java Persistence API (JPA) applications. This file specifies the configuration details for a JPA persistence unit, which defines how the application interacts with the database. For instance, you can figure out which database type is being used by the “hibernate.dialect” property:

<property name="hibernate.dialect" value="org.hibernate.dialect.H2Dialect"/>

In our case, the ‘hibernate.dialect’ is set to "org.hibernate.dialect.H2Dialect", which indicates that the application is using the H2 database.

The database URL and location where the database files are stored are specified by the “hibernate.connection.url” property:

<property name="hibernate.connection.url" value="jdbc:h2:file:./DB;DB_CLOSE_DELAY=-1"/>

From this we can see that the database files are stored in a file named “DB” in the current directory of the application (the ”./” notation in “file:./DB” represents the current working directory of the application).

4. The JUnit test called “JpaTest” was successfully added under src/test/java in a new package no.hvl.dat250.jpa.tutorial.relationshipexample.
5. All the tests succeeded.

To answer the question: “Where do the getter/setter used in setUp() method come from?”

- getTransaction(); is from the interface used to interact with the persistence context: public interface EntityManager extends AutoCloseable
- getResultList(); is from the interface used to control query execution: public interface Query
- setDescription() is from the public class Family
- getMembers() is from the public class Family
- setFirstName() is from the public class Person
- setLastName() is from the public class Person
- setFamily() is from the public class Person
    

# Experiment 2: Banking/Credit Card example JPA

### URL to my code for experiment 2:
https://github.com/h591296/DAT250-JPA-Tutorial.git

### Technical challenges I encountered and how I tried to resolve them

I started implementing the domain model by establishing the essential class variables, such as "id" and "name" within the 'Customer' class. Subsequently, I proceeded to establish the associations between the various classes involved.

After what I thought was a successful mapping, I started adding 'get' and 'set'-methods for the variables. This part also took longer than expected because the method names I used did not match the ones in the test-class. Also, I tried to use Lists for the to-many mappings, as shown in the lecture about JPA. This also caused the tests to fail, and it took me a long time to figure out that I should use Sets instead.

Once I fixed the method names and changed the Lists into Sets, my tests started passing. A classmate showed me that it was possible use Lombok's '@Getter' and '@Setter' to automatically generate these methods, it made the code look cleaner.


1. Where is the database? Explain the used database and how/when it runs.


2. Can you provide the SQl used to create the table Customer (Hint: Hibernate is used for the object-relational-mapping)?


3. Find a way to inspect the database tables being created and attach a screenshot of the database schema to your report. Do the created tables correspond to your initial thoughts regarding the exercise?
