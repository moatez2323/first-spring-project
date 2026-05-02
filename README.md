# First Spring Boot Project – Task 1

A simple Spring Boot web application built as part of the Spring Framework course at **Akademia Finansów i Biznesu Vistula**.

---

## 📋 Project Description

This is a beginner Spring Boot application demonstrating:
- Creating a Spring Boot project from scratch using Spring Initializr
- Writing a Spring MVC Controller
- Handling HTTP GET requests
- Using the `@ResponseBody` annotation
- Returning a Thymeleaf HTML view with dynamic data
- Serving static image resources

---

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| Java | Programming language |
| Spring Boot | Application framework |
| Spring Web (MVC) | HTTP request handling |
| Thymeleaf | HTML template engine |
| Lombok | Boilerplate code reduction |
| Maven | Build and dependency management |

---

## 📁 Project Structure

```
first-project-java/
├── src/
│   └── main/
│       ├── java/
│       │   └── pl/edu/vistula/first_project_java/
│       │       ├── FirstProjectJavaApplication.java   ← Entry point
│       │       └── controller/
│       │           └── HelloController.java           ← Controller
│       └── resources/
│           ├── templates/
│           │   └── greeting.html                      ← Thymeleaf view
│           └── static/
│               └── vistula.png                        ← Static image
└── pom.xml
```

---

## 🚀 How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/moatez2323/first-spring-project.git
   ```

2. Navigate to the project folder:
   ```bash
   cd first-spring-project/first-project-java
   ```

3. Run the application using Maven:
   ```bash
   ./mvnw spring-boot:run
   ```

4. The application starts on **port 8080** by default.

---

## 🌐 Endpoints

### 1. `GET /`

Returns a plain text greeting message directly in the browser.

**URL:** `http://localhost:8080/`

**Method:** `GET`

**Response:**
```
Hello Vistula, in my first Spring controller.
```

> This endpoint uses `@GetMapping("/")` and returns a plain String directly to the HTTP response body.

---

### 2. `GET /greeting`

Returns an HTML page with a personalised greeting, a programmer joke, and the Vistula logo image.

**URL:** `http://localhost:8080/greeting?name=Vistula`

**Method:** `GET`

**Query Parameter:**

| Parameter | Required | Default | Description |
|---|---|---|---|
| `name` | No | `World` | The name to greet |

**Example Requests:**

- With name: `http://localhost:8080/greeting?name=Vistula`
- Without name: `http://localhost:8080/greeting` → defaults to `World`

---





> Navigating to `http://localhost:8080/greeting` without a `name` parameter shows **"Hello, World!"**, the programmer joke, and the Vistula logo.

---

### `GET /greeting?name=Vistula` – With name parameter

> Navigating to `http://localhost:8080/greeting?name=Vistula` shows **"Hello, Vistula!"** instead.

---

## 📖 Code Explanation

### `FirstProjectJavaApplication.java`
The entry point of the Spring Boot application. The `@SpringBootApplication` annotation enables auto-configuration, component scanning, and configuration support. The `main` method launches the embedded Tomcat server on port 8080.

### `HelloController.java`
The controller class annotated with `@Controller`, which marks it as a Spring MVC component responsible for handling HTTP requests.

- **`hello()` method** – mapped to `GET /`. Returns a plain String directly to the HTTP response body.
- **`greeting()` method** – mapped to `GET /greeting`. Accepts an optional `name` query parameter (defaults to `"World"`), adds it to the Spring `Model`, and returns `"greeting"` which Spring resolves to the `greeting.html` Thymeleaf template.

### `greeting.html`
A Thymeleaf template that dynamically renders the `name` attribute passed from the controller using `th:text="'Hello, ' + ${name} + '!'"`. It also displays a static image loaded from the `/static` resources folder using `th:src="@{/vistula.png}"`.

---

## 👤 Author

**Moatez** – Akademia Finansów i Biznesu Vistula  
Course: Spring Framework Apps – Task 1  
## 🖼️ Screenshots

### `GET /greeting` – Default (no name parameter → "World")<img width="1919" height="1079" alt="Screenshot 2026-05-02 223127" 
            src="https://github.com/user-attachments/assets/5162c6a8-ab22-40a7-94b4-2066f0c5ccef" />

