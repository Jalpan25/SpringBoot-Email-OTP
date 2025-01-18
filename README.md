
# SpringBoot-Email-OTP

This project demonstrates an email-based OTP (One Time Password) authentication system using Spring Boot and MySQL. Follow the steps below to set up and run the project.

## Prerequisites

1. Java 8 or higher.
2. MySQL database.
3. Maven.
4. An email account with app-specific password enabled (for Gmail).
5. A code editor (e.g., IntelliJ IDEA, Eclipse, or VS Code).

## Steps to Set Up the Project

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/Jalpan25/SpringBoot-Email-OTP.git
   ```

2. **Open the Project in Your IDE:**
   Navigate to the cloned repository and open it in your preferred IDE.

3. **Configure the `application.properties` File:**
   - Open the `src/main/resources/application.properties` file.
   - Update the following values:
     ```properties
     spring.datasource.url=jdbc:mysql://localhost:3306/your-db-name
     spring.datasource.username=your-username
     spring.datasource.password=your-password

     spring.mail.username=your-email
     spring.mail.password=your-app-password
     ```
   - Replace `your-db-name`, `your-username`, and `your-password` with your MySQL database name, username, and password, respectively.
   - Replace `your-email` with your email address.
   - Replace `your-app-password` with the 16-character app-specific password generated for your email.

4. **Run the Project:**
   - Use Maven to build and run the project:
     ```bash
     mvn spring-boot:run
     ```

5. **Access the Application:**
   - The application will be available at `http://localhost:8080`.

## Notes:

1. **Database Initialization:**
   - The property `spring.jpa.hibernate.ddl-auto=create` ensures that the database tables are created automatically. You can change it to `update` for future runs to preserve data.

2. **Email Configuration:**
   - Ensure that your email account is configured to allow sending emails via SMTP.
   - For Gmail, enable "Allow less secure apps" or create an app-specific password.

3. **Secure Sensitive Information:**
   - Avoid hardcoding sensitive information like email credentials in your code.
   - Use environment variables or a secure secrets manager for production environments.

## Features

- Sends a One Time Password (OTP) to the user's email address.
- Verifies the OTP to authenticate the user.

## Contributing

Contributions are welcome! Feel free to fork this repository, make changes, and submit a pull request.

## License

This project is licensed under the [MIT License](LICENSE).

---

Feel free to reach out if you encounter any issues or have suggestions for improvements!


