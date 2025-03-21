﻿# week3-api-lab

API Documentation
This API provides authentication and product-related services as part of a microservices-based application.

Technologies Used
- Node.js
- Express.js
- MongoDB (if applicable)
- JWT for authentication

Installation
1. Clone the repository:
   git clone <repository-url>
   cd <project-directory>

2. Install dependencies:
   npm install
  
3. Start the server:
   node server.js
   

API Endpoints

Authentication Service
The authentication service allows users to register, log in, and access protected routes.

Register a New User
- Endpoint: POST /register
- Request Body:
  {
    "username": "example_user",
    "password": "secure_password"
  }
- Response:
  {
    "message": "User registered successfully"
  }
  
How it Works:
The server receives the request and validates the input.
The password is hashed for security before storing it in the database.
A success message is returned if the registration is successful.


User Login
Authenticates a user and returns a JWT token for authorization.
- Endpoint: POST /login
- Request Body:
  {
    "username": "example_user",
    "password": "secure_password"
  }
- Response:
  {
    "token": "your_jwt_token"
  }
  
How it Works:
The server checks if the username exists in the database.
The entered password is compared with the stored hashed password.
If authentication is successful, a JWT token is generated and sent to the user.
This token must be used in protected routes.


Protected Route
Provides access to specific users who are authenticated.
- Endpoint: GET /protected
- Headers:
  {
    "Authorization": "Bearer your_jwt_token"
  }
- Response:
  {
    "message": "Access granted to protected route"
  }

How it Works:
The server verifies the provided JWT token.
If valid, the user is granted access to the protected content.


Product Service
The product service handles retrieving product information.

Fetch All Products
- Endpoint: GET /products
- Response:
  [
    {
      "id": 1,
      "name": "Product 1",
      "price": 100.0
    },
    {
      "id": 2,
      "name": "Product 2",
      "price": 200.0
    }
  ]

How it Works:
The server fetches the list of products from the database or a predefined array.
The products are returned as a JSON response.


Testing the API
Use Postman or cURL to test the API endpoints.

Postman – To test API endpoints by sending requests and viewing responses.
cURL – Command-line tool for making API requests.


This API is designed to: 
- Provide secure authentication using JWT.
- Allow user registration and login.
- Grant access to protected routes.
- Fetch and display products in the product service.


Contributors
- Karl Cedrick R. Namuco
- Ia Mary R. Sorio

License
This project is licensed under the MIT License.

