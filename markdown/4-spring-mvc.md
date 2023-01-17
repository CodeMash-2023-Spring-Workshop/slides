## Before we begin

```bash
git clone https://github.com/CodeMash-2023-Spring-Workshop/runnerz-ui
cd runnerz-ui
./mvnw
```

---

## Spring MVC

- Model
- View
- Controller

Notes:
- The Model-View-Controller (MVC) is a software architectural pattern
- three main components: the model, the view, and the controller.
- Model
- Model is responsible for managing the data of the application.
- It includes the logic for storing and manipulating data
- as well as the rules for how that data can be accessed and modified.
- View
- Responsible for presenting the data to the user.
- Graphics, text, images, and forms etc.
- Controller
- Responsible for handling user input and interactions.
- It receives requests from the view
- processes them using the model
- and then updates the view as needed.
- The pattern
- Helps to divide the complexity of an application
- into smaller, more manageable pieces
- makes it easier to develop, maintain, and test the application.

---

## Spring Web Starter

Notes:
- DispatcherServlet
- Uses Spring to discover the components
- Sets up mapping, views, etc
- Building on IoC
- Building on Dependency Injection

---

## Runnerz-UI

Notes:
- Building the backend
- Show the UI

---

## Static HTML

```html
<body>
<p>Endpoints</p>
<ul>
    <li>/api/hello</li>
    <li>/api/runs</li>
</ul>
</body>
```

Notes:
- src/main/resources/static
- src/main/resources/public_html

---

## Actuator Endpoints

```text
management.endpoints.enabled-by-default=true
```

Notes:
- /actuator/mappings
- /actuator/beans
- /actuator/env

---

## Request Logging

```java
@Configuration
public class RequestLoggingConfig {

    @Bean
    public CommonsRequestLoggingFilter logFilter() {
        CommonsRequestLoggingFilter crlf
                = new CommonsRequestLoggingFilter();
        crlf.setIncludeQueryString(true);
        crlf.setIncludePayload(true);
        crlf.setMaxPayloadLength(10000);
        crlf.setIncludeHeaders(true);
        crlf.setAfterMessagePrefix("REQUEST DATA: ");
        return crlf;
    }
}
```

---

## Configurable Logging

```text
logging.level.org.springframework.web.filter.CommonsRequestLoggingFilter=DEBUG
```

Notes:
- http://localhost:8080/actuator/loggers

---

## HelloController

```java
@RestController
@RequestMapping("/api/hello")
public class HelloController {
    private static final String template = "Hello, %s!";

    @GetMapping("/")
    public String hello(@RequestParam(value = "name", defaultValue = "CodeMash") String name) {
        return String.format(template, name);
    }
    
}
```

Notes:
- Creating an endpoint
- Get requests
- Parameter Mapping
- Default Values

---

## Create A Run

```java
@RestController
@RequestMapping("/api/runs")
public class RunController {

    AtomicInteger count = new AtomicInteger();
    private final RunService runService;
    //...
}
```
Notes:
- RequestMapping

---

## Edit a Run

