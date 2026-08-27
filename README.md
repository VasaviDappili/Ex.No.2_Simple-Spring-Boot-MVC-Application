# Exp_2_Simple-Spring-Boot-MVC-Application
# Name: Dappili Vasavi
# Register Number:212223040030

## AIM:
To develop a Simple Spring Boot MVC (Model-View-Controller) Application that uses a Controller to handle HTTP requests, a Model to pass data, and a View (Thymeleaf) to render dynamic HTML pages.

## ALGORITHM:
Create a New Spring Boot Project:

Use Spring Initializr

Add dependencies:

Spring Web

Thymeleaf

Set Up Project Structure:

Create the main class annotated with @SpringBootApplication

Create a Controller class using @Controller

Add HTML templates under src/main/resources/templates

Create a Controller:

Define a method to handle HTTP GET requests using @GetMapping

Return a view name (HTML page name) from the controller

Pass data to the view using Model object

Create a Model (Optional):

Define a simple POJO class if you need to pass structured data to the view

Create View Pages (HTML using Thymeleaf):

Create an HTML file inside the templates folder

Use Thymeleaf syntax (e.g., ${name}) to render dynamic content

Run the Application:

Run the Spring Boot application from your IDE or command line

Access the Application:

Open a browser and navigate to http://localhost:8081/
## PROGRAM
<img width="674" height="560" alt="image" src="https://github.com/user-attachments/assets/2808c219-5f41-46a4-97c3-e8782e850904" />


### pom.xml :

```
<project xmlns="http://maven.apache.org/POM/4.0.0" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
	xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 https://maven.apache.org/xsd/maven-4.0.0.xsd">
	<modelVersion>4.0.0</modelVersion>
	<parent>
		<groupId>org.springframework.boot</groupId>
		<artifactId>spring-boot-starter-parent</artifactId>
		<version>4.1.0</version>
		<relativePath/> <!-- lookup parent from repository -->
	</parent>
	<groupId>com.example</groupId>
	<artifactId>ajw-exp-2</artifactId>
	<version>0.0.1-SNAPSHOT</version>
<properties>
		<java.version>21</java.version>
	</properties>
	<dependencies>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-thymeleaf</artifactId>
		</dependency>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-webmvc</artifactId>
		</dependency>

		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-thymeleaf-test</artifactId>
			<scope>test</scope>
		</dependency>
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-webmvc-test</artifactId>
			<scope>test</scope>
		</dependency>
	</dependencies>

	<build>
		<plugins>
			<plugin>
				<groupId>org.springframework.boot</groupId>
				<artifactId>spring-boot-maven-plugin</artifactId>
			</plugin>
		</plugins>
	</build>

</project>

```

### AjwExp2Application.java (Main Class):

```
package com.example.ajw.exp_2;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

@SpringBootApplication
public class AjwExp2Application {

    public static void main(String[] args) {
        SpringApplication.run(AjwExp2Application.class, args);
    }
}
```

### HomeController.java (Controller):

```
package com.example.ajw.exp_2;

import org.springframework.stereotype.Controller;
import org.springframework.ui.Model;
import org.springframework.web.bind.annotation.GetMapping;

@Controller
public class HomeController {

    @GetMapping("/")
    public String homePage(Model model) {
        model.addAttribute("message", "Welcome to Spring Boot MVC!");
        return "index";
    }
}
```
### index.html (View – inside src/main/resources/templates/):

```
<!DOCTYPE html>
<html xmlns:th="http://www.thymeleaf.org">
<head>
    <title>Spring MVC</title>
</head>
<body>
<h1>Hello,Ankitha</h1>
<h1 th:text="${message}">Default Message</h1>

</body>
</html>
```
### application.properties:
```
spring.application.name=ajw-exp-2
server.port=8081

```
 
# Output:
<img width="1920" height="1080" alt="exp2 ajw output" src="https://github.com/user-attachments/assets/f84d1986-f7bd-454f-a1c7-ef534aac58c6" />


### Result

The Simple Spring Boot MVC Application was successfully developed and executed. The Controller handled the HTTP request, the Model passed data to the View, and Thymeleaf rendered the dynamic HTML page successfully in the browser. The application displayed the welcome message along with the personalized greeting.
