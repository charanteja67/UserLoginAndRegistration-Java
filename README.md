# UserLoginAndRegistration-Java

This project is a simple user registration and login system built using Java, JSP, Servlets, JDBC, HTML,CSS and Bootstrap.

## Prerequisites

Before you begin, ensure you have met the following requirements:
- JDK 8 or higher
- Apache Tomcat 7
- MySQL Server
- MySQL Workbench
- An IDE like IntelliJ IDEA, Eclipse, or NetBeans


## Database Setup

1. Open MySQL Workbench.
2. Create a new database named `Userinfo`.
3. Execute the following SQL script to create the necessary table:

    ```sql
    create database Userinfo;
    use Userinfo;
    create table users(id int primary key auto_increment,uname varchar(50),upwd varchar(50),uemail varchar(50),umobile varchar(20));
    desc users;
    select*from users;
    ```

## Configuration

1. Open the project in your IDE.
2. Navigate to the `src/main/java/com/example/util/DatabaseConnection.java` file.
3. Replace `your-sql-password` with your MySQL Workbench password:

    ```java
    public class DatabaseConnection {
        private static final String URL = "jdbc:mysql://localhost:3306/userdb";
        private static final String USER = "root";
        private static final String PASSWORD = "your-sql-password";

        public static Connection getConnection() {
            Connection connection = null;
            try {
                Class.forName("com.mysql.cj.jdbc.Driver");
                connection = DriverManager.getConnection(URL, USER, PASSWORD);
            } catch (Exception e) {
                e.printStackTrace();
            }
            return connection;
        }
    }
    ```

## Usage

1. Start your Apache Tomcat 7 server.
2. Deploy the project to Tomcat.


### Registration Page

- Access the registration page 
- Enter your desired username, password, and email to register.

### Login Page

- Access the login page
- Enter your registered username and password to log in.

