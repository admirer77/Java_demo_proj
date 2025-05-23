```markdown
# Simple Java Hello World Application with Maven

This repository contains a basic "Hello World" Java application, structured as a Maven project. It's designed to be a straightforward example for anyone looking to understand or practice fundamental Maven concepts, including project structure, building, and testing.

## Project Description

This application simply prints "Hello, Maven World!" to the console. It serves as a minimal working example to demonstrate how to set up, build, and run a Java project using Apache Maven.

## File Structure

The project adheres to the standard Maven directory layout. This structure helps Maven understand where to find source code, resources, and tests.

```
.
├── src
│   ├── main
│   │   ├── java
│   │   │   └── com
│   │   │       └── yoni
│   │   │           └── hellojava
│   │   │               └── Main.java
│   │   └── resources
│   └── test
│       ├── java
│       │   └── com
│       │       └── yoni
│       │           └── hellojava
│       │               └── MainTest.java
│       └── resources
└── pom.xml
```

-   `src/main/java`: Contains the main application source code.
-   `src/main/resources`: Contains application resources (e.g., configuration files, properties).
-   `src/test/java`: Contains the unit test source code.
-   `src/test/resources`: Contains test resources.
-   `pom.xml`: The Project Object Model file, which is the core configuration file for Maven. It defines project dependencies, build plugins, and other project metadata.

## Building the Project

To build the project, navigate to the root directory of the project (where `pom.xml` is located) in your terminal and execute the following Maven command:

```bash
mvn clean install
```

-   `clean`: This phase cleans up the `target` directory, removing any previously compiled classes or build artifacts.
-   `install`: This phase compiles the source code, runs tests, packages the compiled code (into a `.jar` file for this project), and then installs the artifact into your local Maven repository.

Upon successful execution, you will find the generated `.jar` file in the `target/` directory.

## Running the Application

After building the project, you can run the application using the `java -jar` command. Make sure you are in the project's root directory.

```bash
java -jar target/hellojava-1.0-SNAPSHOT.jar
```

(Note: The exact JAR filename might vary slightly based on the version defined in `pom.xml`.)

Alternatively, you can use the Maven Exec Plugin to run the application directly:

```bash
mvn exec:java -Dexec.mainClass="com.yoni.hellojava.main"
```

## Testing the Application

Maven automatically runs any unit tests found in `src/test/java` during the `test` phase (which is part of `install`). To explicitly run only the tests, use:

```bash
mvn test
```

## Maven Repository ID (for practice)

When practicing Maven, especially with advanced topics like deploying artifacts to a remote repository, you might need to configure a `<repository>` or `<distributionManagement>` section in your `pom.xml` or `settings.xml`.

For local practice or setting up a dummy repository, you can use any descriptive id you prefer. For example, if you were to define a local file system repository for practice, you might use an ID like `my-local-dev-repo`:

```xml
<repositories>
    <repository>
        <id>my-local-dev-repo</id>
        <name>My Local Development Repository</name>
        <url>file://${project.basedir}/local-repo</url>
    </repository>
</repositories>
```

This id (`my-local-dev-repo` in this case) is a unique identifier for that specific repository configuration within Maven. It's crucial when Maven needs to differentiate between multiple repositories for dependency resolution or artifact deployment. For a simple "Hello World" application that doesn't deploy to a remote repository, this concept is more for understanding future Maven usage.
```
