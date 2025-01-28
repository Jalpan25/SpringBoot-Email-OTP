
# SpringBoot-Email-OTP

This project demonstrates an email-based OTP (One Time Password) authentication system using Spring Boot and MySQL. Follow the steps below to set up and run the project.

---

## Prerequisites

1. Java 8 or higher.
2. MySQL database.
3. Maven.
4. An email account with app-specific password enabled (e.g., for Gmail).
5. A code editor (e.g., IntelliJ IDEA, Eclipse, or VS Code).

---

## Steps to Set Up the Project

### 1. Clone the Repository
   ```bash
   git clone https://github.com/Jalpan25/SpringBoot-Email-OTP.git
   ```

### 2. Open the Project in Your IDE
   - Navigate to the cloned repository.
   - Open the project in your preferred IDE.

### 3. Configure the `application.properties` File
   - Locate the file at `src/main/resources/application.properties`.
   - Update the following fields with your own values:
     ```properties
     spring.datasource.url=jdbc:mysql://localhost:3306/your-db-name
     spring.datasource.username=your-username
     spring.datasource.password=your-password

     spring.mail.username=your-email
     spring.mail.password=your-app-password
     ```
   - Replace:
     - `your-db-name` with your MySQL database name.
     - `your-username` and `your-password` with your MySQL credentials.
     - `your-email` with your email address.
     - `your-app-password` with the app-specific password for your email account.

### 4. Run the Project
   - Use Maven to build and start the application:
     ```bash
     mvn spring-boot:run
     ```

### 5. Test the Application with Postman
   - **Send OTP**:
     1. Set the method to `POST` and the URL to `http://localhost:8080/send-otp`.
     2. Add the following JSON to the body (select raw):
        ```json
        {
            "email": "example@example.com"
        }
        ```
     3. Send the request. Check your email for the OTP.
   - **Verify OTP**:
     1. Set the method to `POST` and the URL to `http://localhost:8080/verify-otp`.
     2. Add the following JSON to the body (select raw):
        ```json
        {
            "email": "example@example.com",
            "otp": "123456"
        }
        ```
     3. Replace `123456` with the OTP you received in your email.
     4. Send the request to verify the OTP.

---

## Notes

1. **Database Initialization**:
   - The property `spring.jpa.hibernate.ddl-auto=create` creates the database tables automatically on the first run.
   - Change it to `update` in the `application.properties` file for subsequent runs to preserve data.

2. **Email Configuration**:
   - Ensure SMTP is enabled for your email account.
   - For Gmail, create an app-specific password if required and use it in `spring.mail.password`.

3. **Secure Sensitive Information**:
   - Avoid hardcoding sensitive details (e.g., email credentials) in the code.
   - Use environment variables or a secrets manager for production environments.

---

## Features

- Sends a One Time Password (OTP) to the user's email address.
- Verifies the OTP for user authentication.

---

## Contributing

Contributions are welcome! Feel free to fork this repository, make improvements, and submit a pull request.

---

## License

This project is licensed under the [MIT License](LICENSE).

---
