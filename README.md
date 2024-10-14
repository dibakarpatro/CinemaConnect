```md
# Customer Information and Username Validation Web App

## Overview

This project is a simple web application that allows users to sign up by submitting their name, gender, email, and phone number. The information is stored in an AWS RDS MySQL database. Additionally, users can validate if their name exists in the database.

## Features

1. **Customer Information Form**: Users can submit their name, gender, email, and phone number.
2. **Username Validation**: Users can check if their name exists in the database.
3. **Database Storage**: All data is stored in an AWS RDS MySQL database.
4. **Thank You Page**: After successful form submission or validation, a thank-you page is displayed.

## Technologies Used

- **Frontend**: HTML, CSS
- **Backend**: PHP
- **Database**: AWS RDS MySQL
- **Hosting**: Can be hosted on an Apache server or similar setup.

## Project Structure

```bash
├── newuser.html         # The form to collect customer data
├── submit.php           # Backend script to handle customer data submission and store in DB
├── submit2.php          # Backend script for username validation
├── validation.html      # The form to validate if a username exists
├── thankyou.html        # Thank you page displayed after successful submission
├── README.md            # This file
```

## Setup Instructions

### 1. Requirements

- PHP installed on the server
- MySQL database (AWS RDS or local MySQL)
- Web server (e.g., Apache, Nginx)

### 2. Database Configuration

- Create an AWS RDS MySQL instance or use an existing MySQL database.
- Create a table named `customers` in your `webapp` database:

```sql
CREATE TABLE customers (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(100),
    gender VARCHAR(10),
    email VARCHAR(100),
    phone VARCHAR(15)
);
```

### 3. Project Deployment

- Clone or download the repository.
- Place the files on your web server (e.g., `/var/www/html` for Apache).
- Update the MySQL credentials in the `submit.php` and `submit2.php` files:

```php
$mysqli = new mysqli('your-rds-endpoint', 'your-username', 'your-password', 'your-database-name');
```

### 4. Accessing the Application

- **Sign Up Form**: Access `newuser.html` in your browser. After submitting the form, the data will be saved in the database.
- **Username Validation**: Access `validation.html` to check if a username exists in the database.

### 5. Troubleshooting

- Ensure the RDS or MySQL database is running and accessible from the web server.
- Check if the web server (Apache or Nginx) is properly configured to handle PHP files.
- Verify the database credentials in the `submit.php` and `submit2.php` files.

## Future Enhancements

- Add validation to check for existing emails during sign-up.
- Implement error handling for failed form submissions.
- Secure the database queries with prepared statements to prevent SQL injection.

## Author

**K Dibakar Patro**

This project was developed as part of a learning exercise to demonstrate AWS and PHP integration.
```

