<div align="center">

# 🍽️ RestauManager

### Restaurant Management System built with Symfony

A full-stack web application designed to manage restaurant operations through dedicated **Admin**, **Waiter**, and **Customer** interfaces.

<br>

![PHP](https://img.shields.io/badge/PHP-8.2+-777BB4?style=for-the-badge&logo=php&logoColor=white)
![Symfony](https://img.shields.io/badge/Symfony-7.4-000000?style=for-the-badge&logo=symfony&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-Database-4169E1?style=for-the-badge&logo=postgresql&logoColor=white)
![Twig](https://img.shields.io/badge/Twig-Templates-BACF29?style=for-the-badge&logo=twig&logoColor=black)
![Bootstrap](https://img.shields.io/badge/Bootstrap-5-7952B3?style=for-the-badge&logo=bootstrap&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-Compose-2496ED?style=for-the-badge&logo=docker&logoColor=white)

</div>

---

## 📌 About the Project

**RestauManager** is a restaurant management web application built with **Symfony 7** following the **MVC architecture**.

The platform provides three dedicated user environments:

- 👨‍💼 **Administrator**
- 🧑‍🍳 **Waiter**
- 👤 **Customer**

Customers can browse the menu and reserve tables, waiters can manage daily reservations and restaurant tables, while administrators have full control over the restaurant through a complete back-office.

The project demonstrates authentication, role-based authorization, CRUD operations, database relationships, REST-style APIs, Doctrine ORM, Twig templates and responsive interfaces.

---

## ✨ Features

### 👤 Customer

- Create an account and log in
- Browse the restaurant menu
- Reserve a table
- View personal reservations
- Manage profile information

### 🧑‍🍳 Waiter

- View today's reservations
- Confirm or cancel reservations
- Monitor restaurant tables
- Update table availability
- Access the restaurant menu

### 👨‍💼 Administrator

- Admin dashboard
- Reservation statistics
- Manage restaurant tables
- Manage dishes
- Manage menus
- Manage users
- Manage reservations
- Monitor restaurant activity

---

## ⚡ Additional Features

- 🔐 Role-based authentication
- 🛡️ Protected routes with Symfony Security
- 📊 Administration dashboard
- 🗄️ Doctrine ORM entities and repositories
- 🔄 Doctrine migrations
- 🧪 Fixtures and Faker demo data
- 📱 Responsive Bootstrap interface
- 🌐 Public restaurant pages
- 🔎 Table availability API
- ❤️ Application health-check endpoint

---

## 🛠️ Tech Stack

| Category | Technology |
|---|---|
| Backend | PHP 8.2+ |
| Framework | Symfony 7.4 |
| Database | PostgreSQL |
| ORM | Doctrine ORM |
| Templates | Twig |
| Frontend | Bootstrap 5 |
| Authentication | Symfony Security |
| Migrations | Doctrine Migrations |
| Demo Data | Doctrine Fixtures + Faker |
| Testing | PHPUnit |
| Environment | Docker Compose |

---

## 🏗️ Project Architecture

```text
RestauManager/
│
├── src/
│   ├── Controller/
│   │   ├── Admin/
│   │   ├── Client/
│   │   ├── Serveur/
│   │   └── Api/
│   │
│   ├── Entity/
│   │   ├── User.php
│   │   ├── Reservation.php
│   │   ├── RestaurantTable.php
│   │   ├── Plat.php
│   │   └── Menu.php
│   │
│   ├── Form/
│   ├── Repository/
│   └── DataFixtures/
│
├── templates/
│   ├── admin/
│   ├── client/
│   ├── serveur/
│   └── public/
│
├── config/
├── migrations/
├── public/
├── tests/
│
├── docker-compose.yml
├── composer.json
└── README.md
```

---

## 🔐 User Roles

```text
ROLE_ADMIN
ROLE_SERVEUR
ROLE_CLIENT
```

Each role has access to its own dashboard and authorized features.

---

## 🚀 Installation

### Requirements

Make sure you have:

```text
PHP 8.2+
Composer
Docker
Docker Compose
Symfony CLI
```

### Clone the repository

```bash
git clone https://github.com/yourusername/RestauManager.git
cd RestauManager
```

### Install dependencies

```bash
composer install
```

### Environment configuration

```bash
cp .env.example .env
```

### Start PostgreSQL

```bash
docker compose up -d
```

### Create the database

```bash
php bin/console doctrine:database:create --if-not-exists
```

### Run migrations

```bash
php bin/console doctrine:migrations:migrate
```

### Load demo data

```bash
php bin/console doctrine:fixtures:load
```

### Start the Symfony server

```bash
symfony server:start
```

Open:

```text
http://127.0.0.1:8000
```

---

## 👥 Demo Accounts

| Role | Email | Password |
|---|---|---|
| 👨‍💼 Admin | `admin@example.com` | `admin123` |
| 🧑‍🍳 Waiter | `serveur@example.com` | `serveur123` |
| 👤 Customer | `client@example.com` | `client123` |

Additional administrator account:

```text
Email: admin@restaurant.com
Password: admin123
```

---

## 🌐 Main Routes

| Feature | Route |
|---|---|
| Home | `/` |
| Login | `/connexion` |
| Register | `/inscription` |
| Public Menu | `/carte` |
| Reservation | `/reserver` |
| Admin Dashboard | `/admin/dashboard` |
| Tables Management | `/admin/tables` |
| Dishes Management | `/admin/plats` |
| Menus Management | `/admin/menus` |
| Users Management | `/admin/utilisateurs` |
| Reservations Management | `/admin/reservations` |
| Waiter Dashboard | `/serveur/` |
| Waiter Reservations | `/serveur/reservations` |
| Customer Dashboard | `/client/dashboard` |
| Health Check | `/status/health` |

---

## 🔌 API

### Available Tables

```http
GET /api/tables-disponibles
```

Example:

```text
/api/tables-disponibles?date=2026-06-01&heure=19:00&nbPersonnes=2
```

The API searches for tables according to:

```text
Date
Time
Number of guests
Availability
```

---

## 🧪 Useful Commands

```bash
# Run migrations
php bin/console doctrine:migrations:migrate

# Load fixtures
php bin/console doctrine:fixtures:load

# Display application routes
php bin/console debug:router

# Run tests
php bin/phpunit
```

---

## 📸 Screenshots

You can add application screenshots inside:

```text
docs/screenshots/
```

Example:

```markdown
![Admin Dashboard](docs/screenshots/admin-dashboard.png)
```

Recommended screenshots:

```text
Admin Dashboard
Restaurant Menu
Reservation Page
Waiter Dashboard
Customer Dashboard
Tables Management
```

---

## 🚧 Future Improvements

- 📧 Email reservation confirmations
- 🔔 Reservation notifications
- 🔍 Advanced reservation filters
- 📊 Advanced restaurant analytics
- 📅 Interactive booking calendar
- 💳 Online payment integration
- 🌙 Dark mode
- 🌍 Multi-language support
- 🧪 More functional tests
- ☁️ Production deployment

---

## 💡 What This Project Demonstrates

This project highlights practical knowledge of:

```text
Symfony MVC Architecture
PHP Object-Oriented Programming
Doctrine ORM
Database Relationships
CRUD Development
Authentication & Authorization
Role-Based Access Control
REST-style APIs
Twig Templates
Responsive UI Development
Database Migrations
Fixtures & Testing
Docker Development Environment
```

---

## 🎯 Project Purpose

RestauManager was created as a full-stack project to demonstrate the development of a structured restaurant management platform using the Symfony ecosystem.

It combines backend development, database management, authentication, authorization and responsive frontend interfaces in one complete application.

---

<div align="center">

### ⭐ RestauManager

**Manage reservations. Organize tables. Simplify restaurant operations.**

Made with ❤️ using **Symfony**

</div>
