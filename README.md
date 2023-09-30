# Login-Page

## Setup & Installation

Make sure you have the latest version of Python installed.

```bash
git clone <repo-url>
```

```bash
pip install -r requirements.txt
```

## Running The App

```bash
python main.py
```

## Viewing The App

Go to `http://127.0.0.1:5000`

# Flask Authentication Blueprint Readme

This Flask application features user authentication using a Blueprint named 'auth'. It allows users to register, log in, and log out. Below is a brief explanation of the key components and functionality of the code.

## Overview

The application is organized into the following parts:
- `auth` Blueprint: Manages user authentication routes.
- `User` model: Represents user data and interacts with the database.
- Password hashing: Uses `werkzeug.security` to securely hash and verify user passwords.
- Session management: Utilizes `flask_login` to handle user sessions.
- HTML templates: Renders login and registration forms using Flask templates.

## Routes and Functionality

### Login
- **Route**: `/login`
- **Methods**: GET and POST
- **Function**: `login()`
- **Description**:
  - If the request method is POST, the function attempts to log in the user.
  - It retrieves the user's email and password from the request.
  - It checks if the email exists in the database, and if so, it compares the hashed password.
  - If the credentials are correct, the user is logged in, and a success message is displayed.
  - If the credentials are incorrect, error messages are displayed.
- **Access Control**: Available to both anonymous and authenticated users.

### Logout
- **Route**: `/logout`
- **Methods**: GET
- **Function**: `logout()`
- **Description**:
  - Logs out the currently authenticated user and redirects to the login page.
- **Access Control**: Only available to authenticated users.

### Registration
- **Route**: `/register`
- **Methods**: GET and POST
- **Function**: `sign_up()`
- **Description**:
  - If the request method is POST, the function attempts to create a new user account.
  - It retrieves the user's email, username, and passwords from the request.
  - It performs various validation checks (email existence, length of fields, password match, password length).
  - If all checks pass, a new user is created, and the user is logged in.
  - A success message is displayed upon successful registration.
- **Access Control**: Available to both anonymous and authenticated users.

### Templates
- The HTML templates used for rendering login and registration forms are `login.html` and `register.html`, respectively.
- These templates incorporate Flask's template engine for dynamic content rendering.

## How to Use
1. Initialize the Flask application and set up the database.
2. Import the `auth` Blueprint in your main application script.
3. Add the `auth` Blueprint to your app using `app.register_blueprint(auth)`.
4. Ensure that the `User` model is defined correctly, including the database schema.
5. Run your Flask application.

## Dependencies
- Flask: The web framework for building the application.
- Flask-Login: Manages user sessions.
- Werkzeug: Provides password hashing functionality.

## Note
- This code is a basic example of user authentication and should be enhanced for production use, including adding email confirmation, user profile pages, and more robust error handling.

Please feel free to reach out if you have any questions or need further assistance!
