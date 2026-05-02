# Spring Boot Project - Task 1

##  Description
This project is a simple Spring Boot web application that demonstrates how to:
- Handle HTTP requests
- Use controllers
- Pass data from backend to frontend
- Render HTML using Thymeleaf

---

##  How to Run
1. Open the project in IntelliJ IDEA
2. Run FirstProjectJavaApplication.java
3. Open browser:
   http://localhost:8080/greeting

---

##  Endpoints

### 🔹 GET /
Returns plain text response:
Hello Vistula, in my first Spring controller.

---

### 🔹 GET /greeting
Returns HTML page using Thymeleaf.

Example:
http://localhost:8080/greeting?name=Moatez

Response:
- Displays dynamic greeting message
- Shows image (Vistula logo)

---

## 🔄 How it Works

1. User sends request from browser
2. Controller receives the request
3. @RequestParam extracts user input (name)
4. Model sends data to HTML page
5. Thymeleaf displays the data dynamically



## 📸 Screenshots


###  Greeting page
![Greeting](images/screenshot1.png)


---

