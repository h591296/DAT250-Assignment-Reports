#### URL to my code for experiment 2:
https://github.com/h591296/DAT250-Assignment-Reports.git


# Experiment 1: JPA tutorial

## Following the JPA tutorial

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

#### Technical challenges I encountered and how I tried to resolve them

I started implementing the domain model by establishing the essential class variables, such as "id" and "name" within the 'Customer' class. Subsequently, I proceeded to establish the associations between the various classes involved. I began on the associations between the 'Bank' and 'CreditCard' classes, as well as the 'CreditCard' and 'Pincode' classes. I considered these associations to be the most straightforward to begin with. When I moved on to the many-to-many associations, I spent a lot of time trying to get these relationships right.

After what I thought was a successful mapping, I started adding 'get' and 'set'-methods for the variables. This part also took longer than expected because the method names I used did not match the ones in the test-class. Also, I tried to use Lists for the to-many mappings, as shown in the lecture about JPA. This also caused the tests to fail, and it took me a long time to figure out that I should use Sets instead.

Once I fixed the method names and changed the Lists into Sets, my tests started passing. A classmate showed me that it was possible use Lombok's '@Getter' and '@Setter' to automatically generate these methods, it made the code look cleaner. When I made the switch, however, my test-class started failing.

I went back to my original code, but even after manually adding the get- and set-methods, the tests still did not works. At this point I was perplexed and quite confused as to why it did not work this time. I started wondering that the first time my tests ran successfully, it was just a "happy accident".

On Thursday, September 14th, I spent a whole 10 hours trying to figure out what was wrong with my code. I tried changing the dependencies, adding (and then removing) empty constructors and '@Override' the toString-method. By the end of the day, my test-class still did not pass. It just gave me a new error each time - so whenever I corrected the error, it would just give me a new one. During all this, I never managed to get my main-class to run without erros. I have added two screenshots of how the error messages was displayed in the output-field in this repository.

As a last-ditch effort, I tried to replace my code with my classmates code (of course I saved my code onto a different file so I could switch back afterwards). I replaced the contents of every class from the domain model, the persistence file, and the pom file. Surprisingly, I was told that it worked on their computer, but on mine, the main method still did not run correctly, although the tests passed. At this point, I am wondering if the problem is within my working environment. For context, I am using an updated version of Visual Studio Code and I have followed every instruction in the previous assignment to ensure that my environment follows all of the recommended requirements.

Additionally, I tried to look into the database, but since my main-method was not working properly, I could not be sure if the tables were set up correctly. I attempted to check the database files, but they did not provide any useful information.

Due to these technical issues, I cannot answer the specific questions given in this assignment:

1. I do not know where the database is or how it it operates because my main-method consistently encountered errors.
2. I can not provide the SQL used to create the 'Customer' table because Hibernate handles the object-relational mapping, and my code is affected by the issues I mentioned.
3. I can not inspect the database tables or provide a screenshot of the schema because of the unresolved errors preventing the main method from running. Hence, I can not confirm is the tables match my initial expectations for the exercise.

I also tried seeking help on Discord, but I noticed that the teaching assistants were not clearly identified among the chat members. I was hoping that a teacher assistant could help me with my questions or review my code for some guidance. Unfortunately, this did not happen.

Due to the fact that I had work commitments on both Friday and Saturday, I could not use any additional time to work on this assignment. By this point, I had invested a significant amount of time troubleshooting my code, and I ultimately concluded that I had already dedicated enough time to figure out the issues with my project.