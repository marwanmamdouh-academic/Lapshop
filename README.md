# LapShop (ASP.NET MVC E-Commerce)

## Overview

LapShop is an academic ASP.NET MVC e-commerce application focused on managing laptop products, categories, sales invoices, and customer orders. The system emphasizes relational data modeling, MVC architecture, and structured navigation between related entities using the Database First approach.

---

## Objectives

* Apply ASP.NET MVC architectural principles
* Model relational data using Database First and Fluent API
* Implement full CRUD operations for products and categories
* Manage sales invoices and customer orders
* Establish clear navigation between products, categories, and invoices
* Implement user authentication and role-based authorization

---

## Technologies Used

* **Language:** C#
* **Framework:** ASP.NET Core MVC
* **ORM:** Entity Framework Core (Database First)
* **Database:** SQL Server
* **Authentication:** ASP.NET Core Identity
* **Frontend:** Razor Views, HTML, CSS
* **Tools:** Visual Studio, Git, GitHub

---

## System Architecture

The project follows the MVC (Model–View–Controller) pattern:

* **Models:** Represent domain entities (Item, Category, SalesInvoice, Customer, Supplier)
* **ViewModels:** Shape data for presentation purposes
* **Controllers:** Handle request flow and data manipulation
* **Views:** Render UI and manage user interaction
* **Business Logic (Bl):** Contains service classes and database context

Entity relationships are defined using **Fluent API**, while **Data Annotations** are applied for validation.

---

## Core Features

### Product Management

* Create new products (Items)
* Edit existing products
* View detailed product information
* Delete products
* Associate products with categories, item types, and operating systems
* Manage product images

### Category Management

* Create, edit, and delete categories
* View all products within a category
* Display categories on the home page

### Sales Invoice Management

* Create and manage sales invoices
* Add items to invoices with quantities and prices
* Track invoice dates and delivery dates
* View detailed invoice information

### Customer Management

* View customer details
* Track customer orders and purchases
* Associate customers with business information

### Supplier & Purchase Management

* Manage supplier information
* Track purchase invoices from suppliers
* Monitor inventory from purchases

### User Authentication

* User registration and login
* Role-based authorization (Admin/User)
* Secure cookie-based authentication
* Password policies and validation

---

## Database Design

### Entity Relationships

* **Category → Items:** One-to-Many relationship
* **Item → ItemType:** Many-to-One relationship
* **Item → OperatingSystem:** Many-to-One relationship
* **Item → ItemImages:** One-to-Many relationship
* **Item → ItemDiscounts:** One-to-Many relationship
* **Customer ↔ Items:** Many-to-Many relationship
* **SalesInvoice → SalesInvoiceItems:** One-to-Many relationship
* **PurchaseInvoice → PurchaseInvoiceItems:** One-to-Many relationship
* **Supplier → PurchaseInvoices:** One-to-Many relationship
* **Customer → BusinessInfo:** One-to-One relationship

Relationships are configured using **Fluent API** to ensure clear data integrity and maintainability.

---

## Project Structure

```
LapShop/
├── Bl/                          # Business Logic Layer
│   ├── LapShopContext.cs        # Entity Framework DbContext
│   ├── ClsCategories.cs         # Category service
│   ├── ClsItems.cs              # Item service
│   ├── ClsSalesInvoice.cs       # Sales invoice service
│   └── ...                      # Other service classes
├── Domains/                     # Domain Models
│   ├── TbItem.cs                # Item entity
│   ├── TbCategory.cs            # Category entity
│   ├── TbSalesInvoice.cs        # Sales invoice entity
│   └── ...                      # Other domain entities
├── LapShop/                     # Main Web Application
│   ├── Controllers/             # MVC Controllers
│   ├── Views/                   # Razor Views
│   ├── Models/                  # ViewModels
│   ├── Areas/                   # Admin & Landing Pages areas
│   ├── wwwroot/                 # Static files (CSS, JS, Images)
│   └── Program.cs               # Application entry point
└── LapShop.sln                  # Solution file
```

---

## Validation & Data Integrity

* Validation rules implemented using Data Annotations
* Required fields and relational constraints enforced
* Password policies (minimum 8 characters, uppercase, non-alphanumeric)
* Unique email requirement for users

---

## Learning Outcomes

* Practical understanding of MVC architecture
* Experience with Database First and Fluent API
* Managing relational data in real-world applications
* Designing structured navigation between connected entities
* Improving data integrity and validation
* Implementing authentication and authorization
* Building multi-layered application architecture

---

## Getting Started

### Prerequisites

* Visual Studio 2022 or later
* .NET 8.0 SDK or later
* SQL Server (LocalDB or full instance)

### Installation

1. Clone the repository
   ```bash
   git clone https://github.com/your-username/LapShop.git
   ```

2. Open `LapShop.sln` in Visual Studio

3. Update the connection string in `appsettings.json` to point to your existing database

4. Run the application
   ```bash
   dotnet run
   ```

---

## License

This project is developed for academic purposes.
