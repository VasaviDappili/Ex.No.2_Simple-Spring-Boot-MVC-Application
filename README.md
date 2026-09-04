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
?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0
         https://maven.apache.org/xsd/maven-4.0.0.xsd">

	<modelVersion>4.0.0</modelVersion>

	<parent>
		<groupId>org.springframework.boot</groupId>
		<artifactId>spring-boot-starter-parent</artifactId>
		<version>3.5.4</version>
		<relativePath/>
	</parent>

	<groupId>com.example</groupId>
	<artifactId>exp2</artifactId>
	<version>0.0.1-SNAPSHOT</version>

	<name>exp2</name>
	<description>Spring MVC Experiment</description>

	<properties>
		<java.version>21</java.version>
	</properties>

	<dependencies>

		<!-- Spring Web -->
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-web</artifactId>
		</dependency>

		<!-- Thymeleaf -->
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-thymeleaf</artifactId>
		</dependency>

		<!-- Testing -->
		<dependency>
			<groupId>org.springframework.boot</groupId>
			<artifactId>spring-boot-starter-test</artifactId>
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

### Exp2Application.java (Main Class):

```
package com.example.exp2;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

@SpringBootApplication
public class Exp2Application {

	public static void main(String[] args) {
		SpringApplication.run(Exp2Application.class, args);
	}

}

```

### HomeController.java (Controller):

```
package com.example.exp2;

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
<html xmlns:th="http://www.thymeleaf.org" lang="">
<head>
    <title>Spring MVC</title>
</head>
<body>
<h1>Hello,Vasavi</h1>
<h1 th:text="${message}">Default Message</h1>

</body>
</html>
```
### application.properties:
```
spring.application.name=exp2
server.port=8080
```
 
# Output:
<img width="1600" height="900" alt="WhatsApp Image 2026-09-04 at 2 04 22 PM" src="https://github.com/user-attachments/assets/c00688ac-e594-4dc5-96e5-8f5bdcd3cefa" />



### Result

The Simple Spring Boot MVC Application was successfully developed and executed. The Controller handled the HTTP request, the Model passed data to the View, and Thymeleaf rendered the dynamic HTML page successfully in the browser. The application displayed the welcome message along with the personalized greeting.
