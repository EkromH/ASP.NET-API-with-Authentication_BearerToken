# ASP.NET API with Authentication (Bearer Token)
# Overview
This project is an ASP.NET Core API that implements authentication using Bearer Tokens. It demonstrates how to set up and secure an API using token-based authentication, allowing users to access endpoints securely.

# Features
* Bearer Token Authentication: Protects API endpoints using Bearer tokens.
* User Registration: Allows users to register with their details.
* Login: Provides functionality for users to authenticate and receive a Bearer token.
* Protected Endpoints: Secures endpoints to ensure only authenticated users can access them.
# Getting Started
To get started with this project, follow these steps:

# Prerequisites
.NET 8 SDK
Visual Studio 2022 (or any preferred IDE for .NET development)


# Setup
* Install Dependencies: Navigate to the project directory and restore dependencies.
dotnet restore

* Configure the Database: Update your appsettings.json file with the appropriate connection string for your database.

* Run Migrations: Apply any pending migrations to set up the database schema.
dotnet ef database update

* Start the Application: Run the application using the following command:
dotnet run

The API will start and listen on https://localhost:5001 (or the port specified in your launchSettings.json).

# API Endpoints
POST /api/Account/registerCustomer: Registers a new customer.

POST /api/Account/login: Authenticates a user and returns a Bearer token.

GET /api/Protected: An example of a protected endpoint that requires authentication.

# Testing
You can test the API using tools like Postman or cURL. Make sure to include the Bearer token in the Authorization header for protected endpoints.

** Example Requests
* Register a New User
POST /api/Account/registerCustomer
Content-Type: application/json

{
  "firstName": "John",
  "lastName": "Doe",
  "email": "john.doe@example.com",
  "password": "yourpassword",
  "isActive": true
}
* Login

POST /api/Account/login
Content-Type: application/json

{
  "email": "john.doe@example.com",
  "password": "yourpassword"
}
* Access Protected Endpoint

GET /api/Protected
Authorization: Bearer <your_token>
