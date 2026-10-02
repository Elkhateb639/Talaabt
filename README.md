<div align="center">

# 🛒 Talabat E-Commerce Web API

A scalable, maintainable **E-Commerce backend** built with **ASP.NET Core Web API**, **Onion Architecture**, and proven software design patterns.

![.NET](https://img.shields.io/badge/ASP.NET_Core-Web_API-512BD4?logo=dotnet&logoColor=white)
![EF Core](https://img.shields.io/badge/EF_Core-SQL_Server-CC2927)
![Redis](https://img.shields.io/badge/Redis-Basket_Cache-DC382D?logo=redis&logoColor=white)
![JWT](https://img.shields.io/badge/Auth-JWT_%2B_Identity-success)
![Architecture](https://img.shields.io/badge/Architecture-Onion-blue)

[![Swagger](https://img.shields.io/badge/Swagger-Live%20API-85EA2D?style=for-the-badge&logo=swagger&logoColor=black)](https://talabat639.runasp.net/swagger/index.html)
[![Application](https://img.shields.io/badge/Application-Google%20Drive-4285F4?style=for-the-badge&logo=google-drive&logoColor=white)](https://drive.google.com/drive/folders/1l5VT2Uzum8_qmbclHix-9-RpSW1kv05U?usp=sharing)

</div>

---

## 📖 Overview

Talabat is a backend API for an e-commerce application. It provides products with advanced querying, a Redis-backed shopping basket, order management, and secure authentication for the Flutter mobile client.

The codebase is organized around **Onion Architecture** so that business logic stays independent from frameworks, databases, and external services.

---

## 🚀 Live Demo

| Resource | Link |
|---|---|
| 📚 **Swagger / OpenAPI** | [talabat639.runasp.net/swagger](https://talabat639.runasp.net/swagger/index.html) |
| 📱 **Mobile Application** | [Download from Google Drive](https://drive.google.com/drive/folders/1l5VT2Uzum8_qmbclHix-9-RpSW1kv05U?usp=sharing) |

The mobile application communicates with the backend through the REST APIs documented in Swagger.

---

## ✨ Key Features

| Area | Highlights |
|---|---|
| 🛍️ **Products** | Filtering, sorting, pagination, search, brands and types |
| 🧺 **Basket** | Redis-backed, fast create / update / delete |
| 📦 **Orders** | Delivery methods, shipping address, order status, totals |
| 🔐 **Auth** | ASP.NET Core Identity, JWT, role-based authorization |
| 🧱 **Architecture** | Onion Architecture, Repository, Unit of Work, Specification |
| 🛡️ **Reliability** | Global exception middleware, standardized validation errors |
| 📚 **Docs** | Swagger / OpenAPI with JWT support |

---

## 🏗 Architecture

```
┌──────────────────────────────────────────────┐
│                   API Layer                  │  Controllers, Middleware, DI setup
├──────────────────────────────────────────────┤
│                Service Layer                 │  Business logic, DTOs, AutoMapper
├──────────────────────────────────────────────┤
│               Repository Layer               │  EF Core, Unit of Work, Redis, Specifications
├──────────────────────────────────────────────┤
│                  Core Layer                  │  Entities, Interfaces, Specifications contracts
└──────────────────────────────────────────────┘
          Dependencies point inward ➜ Core
```

---

## 🛍️ Products

The Products module manages and retrieves product data.

- Get all products and get product by ID
- Filter by **brand** and **product type**
- Search by name
- Sort products
- Pagination
- Product details and images

Queries are built with the **Specification Pattern**, which keeps filtering, sorting, and paging logic reusable and out of repositories and services.

---

## 🧺 Basket

Baskets are stored in **Redis** for fast access and to avoid unnecessary database round trips.

- Get, create, update, and delete a basket
- Add products and update quantities
- Remove products from the basket

```
Client ➜ Basket API ➜ Basket Service ➜ Redis
```

**Why Redis?** Basket data changes frequently and is temporary. In-memory storage gives fast reads and writes and keeps load off SQL Server.

---

## 📦 Orders

The Orders module handles the full order creation process. An order contains:

- Buyer information
- Basket items and product information
- Delivery method and shipping address
- Order status
- Subtotal, delivery cost, and total amount

```
Client ➜ Orders Controller ➜ Order Service
                               ├── Get basket
                               ├── Get delivery method
                               ├── Create order
                               └── Save changes ➜ SQL Server
```

## 🛠️ Tech Stack

| Technology | Usage |
|---|---|
| C# / ASP.NET Core Web API | Backend API |
| Entity Framework Core | ORM / data access |
| SQL Server | Main and Identity databases |
| ASP.NET Core Identity | User management |
| JWT | Authentication |
| Google.Apis.Auth | Google Sign-In token validation |
| Redis | Basket storage |
| AutoMapper | Object mapping |
| Swagger / OpenAPI | API documentation |
| Dependency Injection | Service management |
| Git & GitHub | Version control |

---



## 👨‍💻 Author

**Ibrahem Elkhatib**

Backend Developer (.NET)

<p align="center">
  <a href="https://github.com/Elkhateb639">
    <img src="https://img.shields.io/badge/GitHub-Elkhateb639-181717?style=for-the-badge&logo=github&logoColor=white" alt="GitHub">
  </a>
  <a href="https://www.linkedin.com/in/ibrahem-elkhatib">
    <img src="https://img.shields.io/badge/LinkedIn-Ibrahem%20Elkhatib-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn">
  </a>
  <a href="mailto:ebrahemtamer639@gmail.com">
    <img src="https://img.shields.io/badge/Email-ebrahemtamer639%40gmail.com-D14836?style=for-the-badge&logo=gmail&logoColor=white" alt="Email">
  </a>
</p>


