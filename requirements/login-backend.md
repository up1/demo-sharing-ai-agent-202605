# REST API :: Login API

## API Specification
* Endpoint: `POST /api/login`
### Request Body:
```
{
  "email": "user@example.com",
  "password": "password123"
}
```

### Response:
* Success (200 OK):
```
{
  "message": "Login successful",
    "token": "jwt_token_here"
}
```

* Error (401 Unauthorized):
```
{
  "message": "Invalid email or password"
}
```

* Error (500 Internal Server Error):
```
{
  "message": "An error occurred while processing the login request"
}
```

## Input validation
* Email field should validate that the input is a valid email address format
* Password field should validate that the input is at least 8 characters long

## Database design for user authentication
* User table:
```
CREATE TABLE users (
  id SERIAL PRIMARY KEY,
  email VARCHAR(255) UNIQUE NOT NULL,
  password_hash VARCHAR(255) NOT NULL,
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
  updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```
Database design considerations:
* The `email` field should be unique to prevent duplicate accounts
* The `password_hash` field should store the hashed password instead of the plain text password for security reasons
* Store the password as a hash using a secure hashing algorithm (e.g., bcrypt) to protect user credentials

## Authentication mechanism
* Use JWT (JSON Web Tokens) for authentication
* Upon successful login, generate a JWT token and return it in the response
* The token should include the user's ID and email as claims
* The token should have an expiration time (e.g., 1 hour)
* The token should be signed with a secret key to prevent tampering