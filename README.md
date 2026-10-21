# Advanced Java Laboratory & Capstone Project Repository

[![Java](https://img.shields.io/badge/Java-17%2B-ED8B00?logo=openjdk&logoColor=white)](https://www.oracle.com/java/)
[![Jakarta EE](https://img.shields.io/badge/Jakarta%20EE-10-F80000?logo=jakartaee&logoColor=white)](https://jakarta.ee/)
[![Apache Tomcat](https://img.shields.io/badge/Apache%20Tomcat-11.0.25-F8DC75?logo=apachetomcat&logoColor=black)](https://tomcat.apache.org/)
[![MySQL](https://img.shields.io/badge/MySQL-8.0%2B-4479A1?logo=mysql&logoColor=white)](https://www.mysql.com/)
[![Apache Maven](https://img.shields.io/badge/Apache%20Maven-3.9%2B-C71A36?logo=apachemaven&logoColor=white)](https://maven.apache.org/)

Welcome to the **Advanced Java Laboratory** repository. This repository
contains the complete laboratory experiment sequence, the Apache Tomcat 11
web runtime container, and the capstone project **ShopSphere**.

All experiment modules and the capstone project reside directly at the
repository root, aligned with the laboratory curriculum sequence.

---

## 🗂️ Repository Directory Structure

```
java_projects/
├── README.md                                          # Master repository documentation (this file)
├── .gitignore                                         # Git ignore rules for build artifacts & runtime logs
│
├── Exp_01_Student_Registration_Form/                  # Exp 1: Desktop Student Registration Form (Swing)
│   ├── Gaurav.java                                    # Swing GUI, validation, event handling & JDBC insert
│   ├── Gaurav.class                                   # Compiled Java bytecode
│   └── lib/mysql-connector-j-26.7.0.jar               # MySQL Connector/J driver for the JDBC insert
│
├── Exp_02_Calculator/                                 # Exp 2: Swing Calculator with MVC Pattern
│   ├── Ccontroller.java                               # Controller (ActionListener event dispatch)
│   ├── Cmodels.java                                   # Model (Arithmetic business logic)
│   ├── Cviews.java                                    # View (Swing JFrame UI components)
│   ├── Main.java                                      # Main entry point
│   └── *.class                                        # Compiled Java bytecode
│
├── Exp_03_Mysql_Connect(JDBC)/                        # Exp 3: JDBC Database Connectivity
│   ├── src/App.java                                   # DriverManager, PreparedStatement DML
│   ├── lib/mysql-connector-j-26.7.0.jar               # MySQL Type-4 JDBC driver JAR
│   ├── bin/App.class                                  # Compiled application bytecode
│   ├── mysql-connector-j-26.7.0/                      # Full MySQL Connector/J distribution
│   └── README.md                                      # JDBC workspace notes
│
├── Exp_04_Server_Client_Basics/                       # Exp 4: TCP Socket Programming
│   ├── server.java                                    # ServerSocket listening on port 5000
│   ├── client.java                                    # Socket client connecting over TCP
│   └── *.class                                        # Compiled server/client bytecode
│
├── Exp_05_RMI/                                        # Exp 5: Java Remote Method Invocation
│   ├── calculator.java                                # Remote interface (java.rmi.Remote)
│   ├── calculator_implementation.java                 # Remote implementation (UnicastRemoteObject)
│   ├── server.java                                    # RMI Server & Registry binding
│   ├── client.java                                    # RMI Client remote invocation
│   └── *.class                                        # Compiled Java bytecode
│
├── Exp_06_Apache_Tomcat/                              # Exp 6: Apache Tomcat 11 Web Container
│   ├── bin/                                           # Startup & shutdown scripts (startup.bat/sh)
│   ├── conf/                                          # Server XML configurations (server.xml, web.xml)
│   ├── lib/                                           # Servlet 6.1 & JSP 4.1 container libraries
│   └── webapps/
│       ├── ROOT/                                      # Default root web application
│       ├── Student_reg_form/                          # Pre-deployed student registration webapp
│       ├── servlet-1.0/                               # Pre-deployed Servlet login application
│       ├── servlet-1.0.war                            # Deployable Servlet login WAR
│       └── mywebapp/                                  # Sample HTML web application
│
├── Exp_06_Servlet_Login_App/                          # Exp 6: Jakarta Servlet Login Application (Maven)
│   ├── pom.xml                                        # Maven build (Jakarta Servlet 6.1)
│   └── src/main/
│       ├── java/com/servlet/                          # AppListener, AuthFilter, Login, Logout, Home
│       └── webapp/index.html                          # Login page
│
├── Exp_07_JSP_Conversion/                             # Exp 7: Dynamic JSP Conversion & JSTL (Maven)
│   ├── README.md                                      # Experiment 7 comprehensive JSP guide
│   └── servlet/
│       ├── pom.xml                                    # Maven build (Jakarta Servlet 6.1, JSTL 3.0)
│       └── src/main/
│           ├── java/com/servlet/                      # HelloServlet, AppListener, AuthFilter, Login, etc.
│           └── webapp/                                # student.jsp, result.jsp, result-jstl.jsp, footer.jsp, style.css
│
└── ShopSphere/                                        # Major Capstone Project: E-Commerce Web App
    ├── pom.xml                                        # Master Maven project descriptor (WAR packaging)
    ├── README.md                                      # ShopSphere developer guide
    ├── PROJECT_STATUS.md                              # Implementation status and handoff notes
    ├── database/shopsphere.sql                        # MySQL schema & seed data
    ├── src/main/java/com/shopsphere/                  # Servlets, DAOs, service, filters, listeners, models
    ├── src/main/webapp/                               # JSP views, custom tag files, JSTL, CSS
    ├── network/src/                                   # TCP inventory socket server/client demo
    ├── rmi/src/                                       # Java RMI inventory service demo
    ├── swing-admin/src/                               # Swing inventory administration demo
    └── extras/src/                                    # Locale, ResourceBundle, URL & JNDI demos
```

---

## 🔬 Laboratory Experiments Overview

### 1. Student Registration Form (Java Swing)
* **Directory**: [`Exp_01_Student_Registration_Form`](Exp_01_Student_Registration_Form)
* **Concepts**: Java Swing GUI controls (`JFrame`, `JLabel`, `JTextField`, `JRadioButton`, `ButtonGroup`, `JCheckBox`), validation logic, `JOptionPane` modal dialogs, submit/reset event handling, JDBC insert into MySQL.
* **Run**:
  ```bash
  cd Exp_01_Student_Registration_Form
  javac -cp "lib/mysql-connector-j-26.7.0.jar" Gaurav.java
  java -cp ".;lib/mysql-connector-j-26.7.0.jar" Gaurav
  ```
  > Requires a MySQL database named `college` with a `student` table
  > (`name`, `roll_number`, `branch`, `gender`) and valid credentials in `Gaurav.java`.

---

### 2. Swing Calculator (MVC Architecture)
* **Directory**: [`Exp_02_Calculator`](Exp_02_Calculator)
* **Concepts**: Model-View-Controller pattern, Swing GUI (`JFrame`, `JLabel`, `JTextField`, `JButton`), `ActionListener`, arithmetic operations, zero-division protection.
* **Run**:
  ```bash
  cd Exp_02_Calculator
  javac *.java
  java main
  ```

---

### 3. MySQL Database Connectivity (JDBC)
* **Directory**: [`Exp_03_Mysql_Connect(JDBC)`](Exp_03_Mysql_Connect%28JDBC%29)
* **Concepts**: Type-4 JDBC driver (`com.mysql.cj.jdbc.Driver`), `DriverManager.getConnection()`, parameterized `PreparedStatement`, SQL injection prevention, DML execution on `college.student`.
* **Run**:
  ```bash
  cd "Exp_03_Mysql_Connect(JDBC)"
  javac -cp "lib/mysql-connector-j-26.7.0.jar" -d bin src/App.java
  java  -cp "bin;lib/mysql-connector-j-26.7.0.jar" App
  ```

---

### 4. Server-Client Basics (TCP Sockets)
* **Directory**: [`Exp_04_Server_Client_Basics`](Exp_04_Server_Client_Basics)
* **Concepts**: Stream sockets, `java.net.ServerSocket`, `java.net.Socket`, TCP handshake, buffered I/O stream communication on port `5000`.
* **Run** (using 2 terminals in `Exp_04_Server_Client_Basics`):
  ```bash
  javac server.java client.java
  java server              # Terminal 1: Starts Server
  java client              # Terminal 2: Connects Client -> Server: Hello Client
  ```

---

### 5. Java Remote Method Invocation (RMI)
* **Directory**: [`Exp_05_RMI`](Exp_05_RMI)
* **Concepts**: Distributed computing, Remote Interface (`java.rmi.Remote`), `UnicastRemoteObject`, `rmiregistry` on port `1099`, `Naming.rebind()`, `Naming.lookup()`.
* **Run** (using 3 terminals in `Exp_05_RMI`):
  ```bash
  javac *.java
  start rmiregistry        # Terminal 1: Starts RMI Registry
  java server              # Terminal 2: Starts RMI Server
  java client              # Terminal 3: Executes Client -> Addition: 30 Subtraction: 10
  ```

---

### 6. Apache Tomcat 11 Web Application Server
* **Directory**: [`Exp_06_Apache_Tomcat`](Exp_06_Apache_Tomcat)
* **Concepts**: Web application container topology, `webapps` deployment directory, `catalina` startup scripts, pre-deployed HTML web applications.
* **Run**:
  ```cmd
  cd Exp_06_Apache_Tomcat\bin
  startup.bat
  ```
  Open these URLs in a browser:
  * `http://localhost:8080/Student_reg_form/`
  * `http://localhost:8080/servlet-1.0/`
  * `http://localhost:8080/mywebapp/`

---

### 6. Servlet Login Application (Jakarta EE & Maven)
* **Directory**: [`Exp_06_Servlet_Login_App`](Exp_06_Servlet_Login_App)
* **Concepts**: Jakarta Servlet 6.1, Maven WAR packaging, session management (`HttpSession`), authentication security filter (`@WebFilter("/home")`), lifecycle listeners (`@WebListener`).
* **Run**:
  ```bash
  cd Exp_06_Servlet_Login_App
  mvn clean package
  ```
  Deploy `target/servlet-1.0.war` to Tomcat:
  ```powershell
  Copy-Item "target\servlet-1.0.war" "..\Exp_06_Apache_Tomcat\webapps\servlet-1.0.war" -Force
  ```
  Start Tomcat and open: `http://localhost:8080/servlet-1.0/` (`admin` / `1234`).

---

### 7. Conversion of HTML into Dynamic JSP (Jakarta EE & Maven)
* **Directory**: [`Exp_07_JSP_Conversion`](Exp_07_JSP_Conversion)
* **Concepts**: Converting static HTML to dynamic JSP (`student.jsp`), MVC dispatching (`forward`), Expression Language (EL: `${studentName}`), JSTL 3.0 Core/XML/SQL tags, modular JSP fragments (`footer.jsp`).
* **Build & Deploy**:
  ```bash
  cd Exp_07_JSP_Conversion\servlet
  mvn clean package
  ```
  Deploy the generated `target/servlet.war` to Tomcat:
  ```powershell
  Copy-Item "target\servlet.war" "..\..\Exp_06_Apache_Tomcat\webapps\servlet.war" -Force
  ```
  Access via browser:
  * JSP Registration Form: `http://localhost:8080/servlet/student.jsp`
  * Dynamic JSP Login: `http://localhost:8080/servlet/index.jsp` (`admin` / `1234`)

---

## 🌟 Major Capstone Project: ShopSphere

* **Directory**: [`ShopSphere`](ShopSphere)
* **Documentation**:
  - [ShopSphere Developer Guide](ShopSphere/README.md)
  - [Implementation Status](ShopSphere/PROJECT_STATUS.md)

### Key Capabilities
- **3-Tier Enterprise Web App**: Jakarta Servlets 6.1 + JSP/JSTL 3.0 + custom tag files (`<tags:productCard/>`, `<tags:rating/>`).
- **Customer Storefront**: Registration, BCrypt password checks, session login/logout, product catalog, search, product details, wishlist, and reviews.
- **Orders & Checkout**: Database-backed cart, stock-aware transactional cash-on-delivery checkout, and user order history.
- **Admin Console**: Product CRUD (including deactivation), categories, order status updates, and customer listing.
- **Security**: Authentication filter, CSRF token filter, and context/session listeners.
- **Distributed Networking**: Multi-threaded TCP inventory socket server/client (educational module).
- **Distributed Objects**: Java RMI remote inventory service/client (educational module).
- **Desktop Administration**: Swing product inventory dashboard (educational module).
- **Database**: MySQL 8+ schema covering users, addresses, categories, products, cart, wishlist, orders, order items, payments, reviews, and coupons.

### Prerequisites
1. Install JDK 17+, Apache Maven, MySQL 8+, and Apache Tomcat 11.
2. Import `database/shopsphere.sql` using:
   ```bash
   mysql -u root -p < database/shopsphere.sql
   ```
3. Configure `SHOPSPHERE_DB_URL`, `SHOPSPHERE_DB_USER`, and
   `SHOPSPHERE_DB_PASSWORD` in the environment running Tomcat.

### Build & Deploy
```bash
cd ShopSphere
mvn clean package
```
Copy `target/shopsphere.war` into Tomcat's `webapps` directory, start Tomcat, and open:
```
http://localhost:8080/shopsphere/
```

### First Admin Account
Register a customer through the UI, then promote that account locally using MySQL:
```sql
USE shopsphere;
UPDATE users SET role = 'ADMIN' WHERE email = 'your-email@example.com';
```
Sign out and back in, then open `/shopsphere/admin`.

### Supplementary Modules
These modules are independent learning examples and are **not wired into the web request flow**:

| Module | Entry Point | Purpose |
| --- | --- | --- |
| `network/src` | `com.shopsphere.network.InventoryServer` / `InventoryClient` | Read-only inventory TCP socket demo |
| `rmi/src` | `com.shopsphere.rmi.InventoryServer` / `InventoryClient` | RMI inventory service demo |
| `swing-admin/src` | `com.shopsphere.swing.AdminDesktop` | Swing inventory dashboard |
| `extras/src` | `com.shopsphere.extras.Demos` | Locale, ResourceBundle, URL & JNDI demos |

Compile the supplementary modules by including the Maven-downloaded dependency
JARs (MySQL Connector/J, BCrypt) on the classpath.

---

## 🛠️ Technologies Used

- **Java 17+**
- **Java Swing**
- **JDBC**
- **MySQL 8+**
- **MySQL Connector/J**
- **Java RMI**
- **Java Sockets**
- **Jakarta Servlets 6.1**
- **JSP, EL & JSTL 3.0**
- **Apache Tomcat 11**
- **Apache Maven**
- **BCrypt**
- **HTML/CSS/JavaScript**

---

## 📚 Purpose of This Repository

This repository serves as a collection of Java development and college
practical projects. It is useful for:

- Practicing Core Java and OOP
- Learning Swing GUI development
- Practicing JDBC and MySQL connectivity
- Understanding client-server socket programming
- Learning Java RMI
- Working with Servlets, JSP, JSTL, and Tomcat
- Maintaining college laboratory projects
- Preparing Java projects for future development and placement practice

---

## ▶️ Getting Started

### Clone the repository

```bash
git clone https://github.com/gourav-swami/java_projects.git
cd java_projects
```

### Java Projects
Open the required project in an IDE such as IntelliJ IDEA, Eclipse,
NetBeans, or VS Code, and make sure JDK 17+ is installed and configured.

### JDBC Projects
1. Install and start MySQL.
2. Create the required database (for example, `college`).
3. Configure the database credentials in the Java project.
4. Add MySQL Connector/J to the classpath if required.
5. Compile and run the application.

### Tomcat Projects
1. Open `Exp_06_Apache_Tomcat`.
2. Build the web application and place the WAR in the `webapps` directory.
3. Start Tomcat using the scripts in `bin`.
4. Open the application through the Tomcat server URL.

---

## 👨‍💻 Author

**Gourav Swami**

GitHub: <https://github.com/gourav-swami>

---

## 📌 Note

Some folders contain compiled `.class` files, libraries, server files, or
generated files because this repository is also maintained as a
practical/learning workspace.

For production projects, it is generally better to use a build system such
as Maven or Gradle and avoid committing generated build artifacts.
