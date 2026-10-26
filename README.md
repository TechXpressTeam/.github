# 🛒 TechXpress — E-Commerce Platform

<p align="center">
  <strong>A Modern Electronics Shopping Experience Built with ASP.NET Core</strong>
</p>

<p align="center">
  An academic team project focused on building a scalable, maintainable, and secure e-commerce platform for electronics.
</p>

---

## 📌 Project Overview

**TechXpress** is a web-based e-commerce platform designed to simplify buying and selling electronic products, including laptops, smartphones, cameras, and accessories.

The platform allows customers to browse products, search and filter listings, manage shopping carts, place orders, and make payments. Administrators can manage products, categories, orders, and inventory through a dedicated admin dashboard.

The application follows **N-Tier Architecture** and uses the Repository Pattern, Unit of Work Pattern, and Dependency Injection to improve maintainability, testability, and separation of concerns.

## 🎯 Project Objectives

- Build a responsive and user-friendly electronics store.
- Apply N-Tier Architecture for clear separation of responsibilities.
- Implement the Repository and Unit of Work patterns.
- Provide secure authentication and role-based authorization.
- Develop shopping cart and order management functionality.
- Integrate Stripe for payment processing.
- Build an administrative dashboard for managing products, categories, and orders.
- Deploy the application to a cloud hosting platform.

## 🛠️ Technology Stack

| Technology | Purpose |
|---|---|
| ASP.NET Core MVC | Web application and presentation layer |
| C# | Application programming language |
| Entity Framework Core | ORM and database access |
| ASP.NET Core Identity | Authentication and user management |
| SQL Server | Relational database |
| Stripe | Payment processing |
| Bootstrap | Responsive UI design |
| jQuery | Client-side interactions |
| DataTables | Admin data management |
| Toastr / Toaster JS | User notifications |
| Microsoft Azure / Hostinger | Deployment and hosting |
| Git & GitHub | Version control and team collaboration |

## 🏗️ System Architecture

The project uses a three-layer architecture.

```text
TechXpress
│
├── TechXpress.Web
│   ├── Controllers
│   ├── Views
│   ├── ViewModels
│   └── wwwroot
│
├── TechXpress.Services
│   ├── Interfaces
│   ├── Services
│   └── Business Logic
│
└── TechXpress.Data
    ├── Entities
    ├── ApplicationDbContext
    ├── Repositories
    └── UnitOfWork
```

### 1. Presentation Layer — TechXpress.Web

Responsible for:
- MVC controllers and Razor views.
- Product browsing and search.
- Shopping cart and checkout interfaces.
- Customer profiles.
- Admin dashboard.
- Client-side interactions and validation.

### 2. Business Logic Layer — TechXpress.Services

Responsible for:
- Business rules and validation.
- Cart calculations and discounts.
- Order processing.
- Inventory and stock rules.
- Product and category operations.
- Payment workflow coordination.

### 3. Data Access Layer — TechXpress.Data

Responsible for:
- Entity Framework Core configuration.
- Database entities and migrations.
- Generic and specialized repositories.
- Unit of Work implementation.
- Database queries and persistence.

## 🧩 Design Patterns

### N-Tier Architecture

Separates presentation, business logic, and data access to improve maintainability and organization.

### Repository Pattern

Provides a consistent abstraction for database operations and separates data access from business logic.

### Unit of Work Pattern

Coordinates related repository operations and supports consistent database transactions. Entity Framework Core's `DbContext` already provides unit-of-work behavior, so the implementation will coordinate its repositories around a shared context.

### Dependency Injection

Uses ASP.NET Core's built-in dependency injection container to provide services and repositories to controllers and other application components.

## 🗄️ Database Design

The initial database design includes the following entities:

| Entity | Description |
|---|---|
| Products | Product details, prices, stock, and images |
| Categories | Product categories |
| Users | Customer and administrator accounts |
| Orders | Order information and status |
| OrderDetails | Items, quantities, and prices per order |
| PaymentTransactions | Payment references and statuses |

Relationships, keys, constraints, and additional fields will be finalized during implementation.

## ✨ Main Features

### Customer Features
- User registration, login, and logout.
- Product browsing and category filtering.
- Product search and details.
- Shopping cart management.
- Checkout and order placement.
- Secure payment processing through Stripe.
- Customer profiles and order history.

### Administrator Features
- Admin dashboard.
- Product creation, editing, and deletion.
- Category management.
- Order management and status updates.
- Inventory management.
- Search, sorting, filtering, and pagination using DataTables.
- Role-based access control.

## 📅 Development Roadmap

### Week 1 — Initial Setup and Product Listings
- Set up the solution and N-Tier projects.
- Configure Entity Framework Core and the database.
- Implement repositories and Unit of Work.
- Configure ASP.NET Core Identity.
- Build product listings, search, and filters.

### Week 2 — Shopping Cart and Admin Panel
- Implement session-based shopping cart functionality.
- Configure Customer and Admin roles.
- Develop product and category management.
- Build the admin dashboard.
- Test cart operations and authorization.

### Week 3 — Orders, Payments, and Profiles
- Implement checkout and order placement.
- Integrate Stripe test payments.
- Handle stock updates and order consistency.
- Develop customer profiles and order history.
- Test payment and order workflows.

### Week 4 — Testing and Deployment
- Improve the responsive user interface.
- Integrate DataTables and notifications.
- Perform functional and security testing.
- Deploy to the selected hosting platform.
- Complete technical documentation and the user manual.

## 🚀 Getting Started

### Prerequisites

Install the following tools before running the project:

- .NET 8 SDK
- Visual Studio 2022 or a compatible IDE
- SQL Server or SQL Server LocalDB
- Git
- A Stripe test account for payment development

### Installation

**1. Clone the repository**

```bash
git clone https://github.com/TechXpressTeam/TechXpress.git
cd TechXpress
```

**2. Configure the database connection**

Add your database connection string to the appropriate configuration file or user secrets.

Never commit real passwords, API keys, or production secrets to GitHub.

**3. Apply Entity Framework Core migrations**

After configuring the actual startup project and `DbContext`, run the appropriate migrations:

```bash
dotnet ef database update
```

**4. Run the application**

After the solution and projects have been created:

```bash
dotnet run --project TechXpress.Web
```

The exact commands and configuration may be adjusted to match the final project structure.

## 🔐 Security Considerations

- Use ASP.NET Core Identity for account management.
- Protect administrative routes with role-based authorization.
- Validate all user inputs on the server.
- Store secrets using User Secrets or secure deployment configuration.
- Use HTTPS in production.
- Verify Stripe payment results on the server.
- Avoid storing raw card details.
- Apply appropriate authorization checks to orders and customer data.

## 👥 Team Collaboration

This project is managed using Git and GitHub.

Recommended workflow:

1. Assign each feature to a team member.
2. Create a separate branch for each task.
3. Commit changes with clear messages.
4. Push the branch to GitHub.
5. Open a Pull Request for review.
6. Merge approved changes into `main`.

Example branch names:

```text
feature/product-listing
feature/identity-authentication
feature/shopping-cart
feature/admin-dashboard
feature/stripe-payments
```

## 🧪 Testing Strategy

Testing will cover:

- Product browsing and search.
- User registration and login.
- Customer and administrator permissions.
- Shopping cart calculations.
- Stock validation and order creation.
- Stripe test payments and payment failures.
- Admin product and order management.
- Input validation and access control.

## ☁️ Deployment

The application is planned for deployment to Microsoft Azure or Hostinger, depending on hosting compatibility and project requirements.

Production deployment will require appropriate database hosting, HTTPS, environment configuration, secure payment settings, and database backups.

## 📚 Documentation

Project documentation will cover:

- System architecture.
- Database schema and entity relationships.
- Repository and Unit of Work implementation.
- API or application endpoints where applicable.
- Installation and configuration.
- User and administrator guides.
- Testing and deployment procedures.

## 📄 Project Status

**Current phase:** Initial setup and architecture planning.

Features and deployment status will be updated as development progresses.

## 📜 License

This project is developed for academic and educational purposes. Licensing and redistribution terms will be defined by the project team.

---

<p align="center">
  <strong>TechXpress — Fast. Smart. Reliable.</strong>
</p>
