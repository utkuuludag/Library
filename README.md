# Library - Enterprise Modular Monolith CMS

![.NET](https://img.shields.io/badge/.NET-8.0-purple)
![Architecture](https://img.shields.io/badge/Architecture-Clean%20%2F%20Onion-green)
![Pattern](https://img.shields.io/badge/Pattern-Modular%20Monolith-blue)
![Database](https://img.shields.io/badge/Database-MSSQL%20%2F%20EF%20Core-red)

## 📖 Project Overview

**Library** is a scalable, enterprise-level Content Management System developed with **.NET 8**. 

Unlike traditional monolithic applications, Library adopts a **Modular Monolith** architecture, ensuring strict boundary separation between business modules (Accounts, Contents, Files, etc.) while maintaining the simplicity of a single deployment unit. The project is designed following **Domain-Driven Design (DDD)** principles and **Clean Architecture** standards.

> **⚠️ Note on Source Code:** > Due to commercial restrictions and NDA agreements regarding the proprietary business logic used in this project, the full source code is not publicly available. This repository serves as a **technical showcase** and architectural documentation of the engineering practices employed.

---

## 🏗️ Architecture & Design

The project is structured to solve common enterprise problems: maintainability, scalability, and testability.

### 1. Modular Monolith Approach
Instead of a "Big Ball of Mud," the application is divided into self-contained modules. Each module encapsulates its own:
- **Domain Layer:** Entities, Value Objects, Enums (No dependencies)
- **Application Layer:** DTOs, Interfaces, Mappers (Depends on Domain)
- **Infrastructure Layer:** DbContext, Repositories, Migrations (Depends on Application)

### 2. Core Principles
- **Onion / Clean Architecture:** The Core layer is at the center, independent of external frameworks or databases.
- **CQRS (Command Query Responsibility Segregation):** Read and Write operations are logically separated for performance optimization.
- **Rich Domain Model:** Business logic resides in entities, not services (anemic model avoidance).

---

## 🛠️ Tech Stack & Tools

| Category | Technologies |
|----------|--------------|
| **Core Framework** | .NET 8, C# 12 |
| **Data Access** | Entity Framework Core (Code First), MSSQL |
| **Architecture** | Modular Monolith, Clean Architecture, N-Layer |
| **Patterns** | Repository, UnitOfWork, CQRS, Dependency Injection |
| **Client Side** | MVC (Razor Views), Bootstrap 5, jQuery |
| **Tools** | Docker, AutoMapper, FluentValidation, Serilog |

---

## 📂 Project Structure (The Proof)

Below is the actual solution structure demonstrating the modular separation:

```text
Library.sln
│
├── 📂 Core  (Shared Kernel)
│   ├── Core.Caching        # Distributed Caching Interfaces
│   ├── Core.Entities       # Base Entities & Aggregate Roots
│   ├── Core.Exceptions     # Custom Exception Handling
│   ├── Core.Interfaces     # Generic Repository & UnitOfWork Contracts
│   └── Core.Localizations  # Multi-language Support
│
├── 📂 Services (Modules)
│   ├── 📂 AccountsService  # Identity & User Management Module
│   │   ├── Accounts.Domain
│   │   ├── Accounts.Application
│   │   └── Accounts.Infrastructure
│   │   
│   ├── 📂 ContentsService  # CMS Content Management Module
│   ├── 📂 FilesService     # File Storage & Management Module
│   └── 📂 UIPreferences    # Dynamic UI Configuration Module
│
└── 📂 Web.CMS (Presentation)
    ├── Controllers
    ├── Views
    └── appsettings.json

📸 Architecture Visuals
Solution Overview (Modular Separation)
(This screenshot demonstrates how modules are isolated within the solution)

Module Internals (Clean Architecture Layers)
(Inside a specific module, strictly following Domain -> Application -> Infrastructure hierarchy)

🔑 Key Features Implemented
Dynamic Role & Permission Management: granular control over user actions.

Multi-Language Support: Database-driven localization for global scalability.

Audit Logging: Tracking user behavior and system changes.

File Management System: Secure upload and storage mechanism.

Background Jobs: Handling non-blocking tasks.

👨‍💻 Author
Utku Uludağ Full Stack Developer & Software Architect Specialized in modernizing legacy systems and building scalable .NET architectures.

LinkedIn Profile
