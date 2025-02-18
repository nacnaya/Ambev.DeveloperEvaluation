Certainly! Below is a detailed README.md file designed to help users clone and run a .NET Core 8 application with RabbitMQ and PostgreSQL using Docker. This guide follows the best practices that a senior developer might consider when preparing documentation.
# Ambev Developer Evaluation - Sales Management API

Assessment project for vacancy at Ambev.

This project designed to handle CRUD operations for managing sales records and implements business logic for calculating discounts based on product quantities. It follows **Domain-Driven Design (DDD)** principles and built using **.NET 8**, **Mediator**, **AutoMapper**, **Entity Framework (EF)**, **RabbitMQ**, **PostgreSQL** and **Docker Compose**.

## RESTful API Design
Clean and well-documented endpoints for client integration, built using **Swagger/OpenAPI** for automatic API documentation.

## Features

### Sales Record Management
Store and manage sales information, including:
- Sale number
- Date of the sale
- Customer
- Branch where the sale occurred
- Products involved in the sale
- Item details such as:
  - Quantity
  - Unit price
  - Discounts
  - Cancellation status

### Business Logic
Implemented discount rules based on item quantity:
- 10% discount for purchases between 4 and 9 items.
- 20% discount for purchases between 10 and 20 items.
- Purchases above 20 identical items are restricted.
- No discounts are applied for quantities below 4 items.

## Prerequisites

Before you begin, ensure you have met the following requirements:

- **Docker**: You should have Docker installed on your machine. [Get Docker](https://docs.docker.com/get-docker/)
- **Git**: Make sure Git is installed to clone the repository. [Get Git](https://git-scm.com/downloads)

## Installation

Follow these steps to get the application up and running locally.

1. **Clone the Repository**

   Start by cloning the repository from GitHub. Open your terminal and run the following command:

   ```bash
   git clone https://github.com/nacnaya/Ambev.DeveloperEvaluation.git

   Navigate to the project directory:
cd sales-api


## Running the Application
The application is containerized using Docker, making it simple to run:

Build and Run the Docker Containers
Use Docker Compose to build and run the application's containers. Execute the command below to start the services:

   ```bash
   docker-compose up --build
   ```
  This command will start the .NET Core application, RabbitMQ, and PostgreSQL together.

## Accessing the API

Once the containers are up, you can access the API via:
[http://localhost:7181](http://localhost:7181)

## Testing the API

Use Postman or another API testing tool to test the following endpoints:

- **POST /sales** – Create a new sale
- **GET /sales/{id}** – Retrieve sale details
- **PUT /sales/{id}** – Modify an existing sale
- **DELETE /sales/{id}** – Cancel a sale
- **PATCH /api/Sales/cancel/{id}** – Cancel a sale
- **PATCH /api/Sales/cancel-item/{saleId}/{itemId}** – Cancel a specific item from a sale
- **GET /sales** – List all sales

## Running Unit Tests

Run unit tests with xUnit:

```bash
dotnet test
```

## Project Structure
Briefly describe the significant components and organization of your project:

/src: Contains the main source code of the .NET Core application.
/tests: Unit and integration tests.


This README structure offers clarity for new developers trying to set up the project environment, detailing the necessary steps for successful configuration and operation. Adjust specific project paths, ports, and credentials to match your project's particular requirements.

