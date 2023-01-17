## Getting started

- java
- javac
- Ant
- Maven
- Gradle

Notes:
- classpath
- libs
- Ant pointed to libs and sources
- Maven and other resolved dependencies
- Gradle added its own Domain Specific Language (DSL)

---

## start.spring.io

Notes:
- web, actuator, configuration
- Maven
- 3.0.1
- Java 17
- groupId: org.codemash
- artifact: runnerz
- name: runnerz
- description: Run Tracker

---

## Command Line "Share"

```bash
https://start.spring.io/#!type=maven-project&language=java&platformVersion=3.0.1&packaging=jar&jvmVersion=17&groupId=org.codemash&artifactId=runnerz&name=runnerz&description=Run%20Tracker&packageName=org.codemash.runnerz&dependencies=actuator,configuration-processor,web
```

Notes:
- Share the project
- Bootstrap projects
- How do we connect to X
- What library for Y
- Are these versions compatible

---

## Another way

```text
curl https://start.spring.io/starter.tgz \
-d type=maven-project \
-d language=java \
-d platformVersion=3.0.1 \
-d packaging=jar \
-d jvmVersion=17 \
-d groupId=org.codemash \
-d artifactId=runnerz \
-d name=runnerz \
-d description=Run%20Tracker \
-d packageName=org.codemash.runnerz \
-d dependencies=actuator,configuration-processor,web \
| tar -xzf -
```

---

#### https://github.com/CodeMash-2023-Spring-Workshop

Notes:
- snapshot branches
- Raise your hand if you are stuck
- Please don't fret

---

## Consistent

```text
Works on my machine.
Works on your machine.
```

Notes:
- start.spring.io
- Click the shareable link
- curl
- Spring Initializr
- Examine pom.xml

---

## pom.xml

---

## Spring Boot Starters

Notes:
- Quick start baked in
- Sane defaults
- Secure by default
- Compatibility
- Consistent
- Framework
- Not required

---

## Dependency Versions

Notes:
- Compatible
- Release Trains

---

## Boot Strapped

Notes:
- Main Application Class
- @SpringBootApplication annotation
- Tests

---

## Test Included

```bash
./mvnw clean test
```

---

## Batteries Included

```bash
./mvnw spring-boot:run
```
Notes:
- mvn wrapper / gradle wrapper
- How to start the application
- IDE
- Maven
- View the application / browser & command-line

---

## Healthy

```bash
http :8080/actuator/health
```

Notes:
- Dependencies / Starters
- Can inject HealthChecks

---

## Break Time? 

## Questions?