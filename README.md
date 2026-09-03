# 🧾 POS System — Smart Point of Sale for Android

> **A modern, full-stack Point of Sale (POS) application for small shops and retail counters — built with Kotlin, Jetpack Compose, Spring Boot, REST APIs, and PostgreSQL.**

[![Android](https://img.shields.io/badge/Android-7.0%2B-brightgreen?logo=android)](https://developer.android.com/)
[![Kotlin](https://img.shields.io/badge/Kotlin-2.x-7F52FF?logo=kotlin&logoColor=white)](https://kotlinlang.org/)
[![Jetpack Compose](https://img.shields.io/badge/Jetpack%20Compose-UI-4285F4?logo=jetpackcompose&logoColor=white)](https://developer.android.com/jetpack/compose)
[![Spring Boot](https://img.shields.io/badge/Spring%20Boot-Backend-6DB33F?logo=springboot&logoColor=white)](https://spring.io/projects/spring-boot)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-Database-4169E1?logo=postgresql&logoColor=white)](https://www.postgresql.org/)
[![REST API](https://img.shields.io/badge/API-REST-0A0A0A)](https://restfulapi.net/)
[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](#-license)

**🌐 Project Website:** `https://pos-app-beta-seven.vercel.app/`  
**📱 Platform:** Android  
**📦 Current Version:** 1.0  
**📥 APK:** Available from the project website

---

## 📌 Overview

**POS System** is a full-stack Android Point of Sale application designed to simplify everyday retail operations.

The application provides a complete flow from **product management → billing → payment → transaction storage → sales reporting** while keeping shop data synchronized through a cloud-hosted backend.

The goal is to evolve the project from a student/portfolio application into a **production-ready POS platform** that can be deployed and used by real businesses.

### What problem does it solve?

Small shops often need a simple way to:

- Manage products and prices
- Create bills quickly
- Record completed sales
- Review transaction history
- Track daily sales
- View financial reports
- Access their data from another device

This project brings those workflows together in a single Android application.

---

# ✨ Features

## 🔐 Authentication & Account Management

- User registration
- Secure login
- Forgot-password workflow
- Account/profile management
- User-specific data access
- Backend authentication and authorization

## 📦 Product Management

- Add products
- Edit product information
- View product catalog
- Search products
- Maintain product prices
- Cloud-backed product storage

## 🧾 Billing & Checkout

- Add products to a cart
- Increase/decrease quantities
- Calculate totals dynamically
- Review the current bill
- Complete checkout
- Save completed transactions

## 💳 Payment Flow

- Dedicated checkout/payment screen
- Record amount collected
- Complete a sale
- Persist transaction data

> **Production note:** Payment processing should be integrated with a certified payment provider before the application is used for real card/UPI/payment transactions. The current application records the checkout flow; it should not be treated as a payment gateway by itself.

## 📊 Dashboard

The dashboard provides a quick overview of shop activity:

- Today's sales
- Quick actions
- Add Product
- Start Billing
- Sales History
- Financial Report

## 📈 Sales & Financial Reports

- Transaction history
- Sales totals
- Profit-related metrics
- Newest-first transaction/report views
- Historical sales visibility

## ☁️ Cloud Synchronization

Products and transactions are stored on a hosted backend rather than only on the device.

This allows an authenticated user to access the same account data from another supported Android device.

## 🆘 Support

- In-app contact/support screen
- Centralized backend communication
- Designed for future issue reporting and support workflows

---

# 🖥️ Application Flow

```text
                    ┌─────────────────┐
                    │   Launch App    │
                    └────────┬────────┘
                             │
                     ┌───────▼────────┐
                     │ Login / Signup │
                     └───────┬────────┘
                             │
                     ┌───────▼────────┐
                     │   Dashboard    │
                     └───────┬────────┘
                             │
          ┌──────────────────┼──────────────────┐
          │                  │                  │
     ┌────▼─────┐       ┌────▼─────┐      ┌────▼──────┐
     │ Products │       │  Billing │      │  Reports  │
     └────┬─────┘       └────┬─────┘      └────┬──────┘
          │                  │                  │
     Add / Edit          Cart / Total       Sales Data
                             │
                       ┌─────▼─────┐
                       │  Payment  │
                       └─────┬─────┘
                             │
                       ┌─────▼──────┐
                       │ Transaction│
                       │   Saved    │
                       └────────────┘
```

---

# 🏗️ System Architecture

The project follows a client-server architecture.

```text
┌─────────────────────────────────────────────────────────┐
│                    Android Application                  │
│                                                         │
│  Jetpack Compose → ViewModel → Repository → Retrofit   │
└──────────────────────────┬──────────────────────────────┘
                           │
                           │ HTTPS / REST API
                           ▼
┌─────────────────────────────────────────────────────────┐
│                    Spring Boot Backend                  │
│                                                         │
│ Controller → Service → Repository → Security            │
└──────────────────────────┬──────────────────────────────┘
                           │
                           │ JPA / Hibernate
                           ▼
┌─────────────────────────────────────────────────────────┐
│                       PostgreSQL                        │
│                                                         │
│ Users • Products • Transactions • Transaction Items     │
└─────────────────────────────────────────────────────────┘
```

### Recommended production deployment

```text
Android App
    │
    │ HTTPS
    ▼
Reverse Proxy / Load Balancer
    │
    ▼
Spring Boot API
    │
    ├── Authentication / Authorization
    ├── Business Logic
    ├── Validation
    ├── Transaction Management
    └── REST APIs
    │
    ▼
Managed PostgreSQL
```

---

# 🛠️ Technology Stack

## Android

| Technology | Purpose |
|---|---|
| Kotlin | Primary programming language |
| Jetpack Compose | Modern declarative UI |
| Android SDK | Mobile platform |
| ViewModel | UI state/business presentation |
| Retrofit | REST API communication |
| Coroutines | Asynchronous operations |
| Navigation | Screen navigation |
| Material Design | UI components |

## Backend

| Technology | Purpose |
|---|---|
| Java / Kotlin | Backend programming |
| Spring Boot | REST API framework |
| Spring Web | HTTP/REST endpoints |
| Spring Data JPA | Database access |
| Hibernate | ORM |
| Spring Security | Authentication & authorization |
| Spring Mail | Password recovery/email workflows |
| Bean Validation | Request validation |

## Database

- PostgreSQL
- JPA/Hibernate
- Relational data model
- Foreign-key relationships
- Database indexes for frequently queried fields
- Transactional operations for critical sales workflows

## Deployment

Recommended production stack:

- Android APK/AAB
- Spring Boot API on a managed cloud service
- Managed PostgreSQL
- HTTPS/TLS
- Environment variables / secrets management
- CI/CD with GitHub Actions
- Centralized logging and monitoring

---

# 📱 Screens

The current application contains the following primary screens:

1. **Login**
2. **Register**
3. **Forgot Password**
4. **Dashboard**
5. **Product Catalog**
6. **Add Product**
7. **Create Bill**
8. **Payment**
9. **Save Transaction**
10. **Transaction History**
11. **Sales Report**
12. **Profile**

Add screenshots to the repository under:

```text
docs/screenshots/
```

Recommended README screenshots:

```text
docs/screenshots/dashboard.png
docs/screenshots/products.png
docs/screenshots/billing.png
docs/screenshots/payment.png
docs/screenshots/transactions.png
docs/screenshots/reports.png
```

Then display them here:

```markdown
<p align="center">
  <img src="docs/screenshots/dashboard.png" width="220"/>
  <img src="docs/screenshots/products.png" width="220"/>
  <img src="docs/screenshots/billing.png" width="220"/>
  <img src="docs/screenshots/reports.png" width="220"/>
</p>
```

---

# 🚀 Getting Started

## Prerequisites

Before running the project locally, install:

- Android Studio
- JDK 17+ (use the version required by your Spring Boot release)
- Android SDK
- Gradle
- PostgreSQL
- Git

Verify your environment:

```bash
java -version
git --version
```

---

# 📥 Clone the Repository

```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git
cd YOUR_REPOSITORY
```

> Replace the repository URL with your actual GitHub repository.

---

# 📱 Android Setup

1. Open the Android project in Android Studio.
2. Configure the required Android SDK.
3. Set the backend API URL for the selected build environment.
4. Sync Gradle.
5. Connect an Android device or start an emulator.
6. Run the application.

### API configuration

Do **not** hard-code production secrets or credentials inside the Android source code.

Use environment/build configuration for values such as:

```text
API_BASE_URL
```

Example:

```text
Debug  → https://api-dev.example.com/
Release → https://api.example.com/
```

---

# ☕ Backend Setup

Clone/open the Spring Boot backend:

```bash
cd backend
```

Create a PostgreSQL database:

```sql
CREATE DATABASE pos_system;
```

Configure the backend using environment variables.

Example:

```text
DB_URL=jdbc:postgresql://localhost:5432/pos_system
DB_USERNAME=postgres
DB_PASSWORD=your_password

MAIL_HOST=smtp.example.com
MAIL_PORT=587
MAIL_USERNAME=your_email
MAIL_PASSWORD=your_app_password

JWT_SECRET=replace_with_a_long_random_secret
```

Then start the backend:

```bash
./mvnw spring-boot:run
```

or:

```bash
./gradlew bootRun
```

depending on the build system used by the repository.

---

# 🔒 Production Security

Before deploying this system for real businesses, the following security controls should be implemented and verified.

### Authentication

- Use strong password hashing such as BCrypt/Argon2
- Use short-lived access tokens
- Use secure refresh-token rotation if refresh tokens are implemented
- Never store plaintext passwords
- Never log passwords or authentication tokens

### Authorization

Every protected API should verify:

```text
Authenticated user
        ↓
User identity
        ↓
Resource ownership
        ↓
Allowed operation
```

For example, one shop user must not be able to request another user's products or transactions simply by changing an ID in an API request.

### API Security

- HTTPS only in production
- Strict request validation
- Authentication on protected endpoints
- Authorization checks
- Rate limiting for sensitive endpoints
- CORS configured for known clients where applicable
- Secure HTTP headers
- No secrets committed to Git
- Production logging without sensitive data

### Database Security

- Use a dedicated database user
- Use strong credentials
- Restrict network access
- Encrypt backups
- Enable automated backups
- Add indexes for high-volume queries
- Use database transactions for critical operations

---

# 💰 Making Billing Reliable

A POS system must treat a completed sale as an important transactional operation.

A recommended flow is:

```text
Create Bill
    ↓
Validate Product IDs
    ↓
Validate Prices / Quantities
    ↓
Calculate Server-Side Total
    ↓
Create Transaction
    ↓
Create Transaction Items
    ↓
Commit Database Transaction
    ↓
Return Success
```

The **server should be the source of truth for final totals**.

Do not trust a total calculated only by the Android client.

For example:

```text
Client total: ₹445
        ↓
Server recalculates:
Product A × 2
Product B × 1
        ↓
Validated total: ₹445
        ↓
Database transaction committed
```

This protects the business logic from accidental inconsistencies and client-side manipulation.

---

# 🔁 Preventing Duplicate Sales

Production POS systems should also handle retries safely.

If the mobile app sends a request and the network fails before receiving the response, the user may retry.

Without protection:

```text
Request 1 → Transaction created
Request 1 → response lost
Retry     → Another transaction created ❌
```

Use an **idempotency key** or another server-side duplicate-protection mechanism:

```text
Request + Idempotency Key
            ↓
       Server checks
            ↓
   ┌────────┴────────┐
   │                 │
Already processed   New request
   │                 │
Return result       Create sale
```

This is an important production-readiness feature.

---

# 🗄️ Suggested Data Model

A scalable initial model can contain:

```text
User
 ├── id
 ├── name
 ├── email
 ├── passwordHash
 └── createdAt

Product
 ├── id
 ├── ownerId
 ├── name
 ├── price
 ├── stockQuantity
 ├── active
 └── createdAt

Transaction
 ├── id
 ├── ownerId
 ├── totalAmount
 ├── paymentMethod
 ├── status
 └── createdAt

TransactionItem
 ├── id
 ├── transactionId
 ├── productId
 ├── quantity
 ├── unitPrice
 └── lineTotal
```

For a real multi-shop product, consider adding:

```text
Shop
 ├── id
 ├── name
 ├── ownerId
 └── createdAt

ShopMember
 ├── shopId
 ├── userId
 └── role
```

This makes it easier to support:

- Owner
- Manager
- Cashier
- Multiple shops
- Multiple devices
- Role-based permissions

---

# 🌍 Production Deployment Plan

## Phase 1 — Development

```text
Android Studio
       ↓
Local Spring Boot
       ↓
Local PostgreSQL
```

## Phase 2 — Staging

```text
Android Debug/Staging Build
       ↓
Cloud Spring Boot API
       ↓
Staging PostgreSQL
```

## Phase 3 — Production

```text
Android Release AAB/APK
       ↓
HTTPS
       ↓
Production Spring Boot API
       ↓
Managed PostgreSQL
       ↓
Automated Backups + Monitoring
```

---

# ☁️ Recommended Cloud Architecture

A practical deployment can use:

```text
                    ┌─────────────────┐
                    │ Android Client │
                    └────────┬────────┘
                             │
                           HTTPS
                             │
                    ┌────────▼────────┐
                    │  Spring Boot    │
                    │   REST API      │
                    └────────┬────────┘
                             │
               ┌─────────────┴─────────────┐
               │                           │
        ┌──────▼──────┐             ┌──────▼──────┐
        │ PostgreSQL  │             │ Email / OTP │
        │   Database  │             │   Service   │
        └─────────────┘             └─────────────┘
```

The marketing/portfolio website can remain deployed separately from the backend API.

---

# 🧪 Testing Strategy

A production POS application should be tested at multiple levels.

### Unit Tests

Test:

- Price calculations
- Cart totals
- Validation
- Authentication logic
- Report calculations
- Business rules

### Integration Tests

Test:

- API + database
- Authentication
- Product CRUD
- Transaction creation
- Password recovery
- Authorization

### Android Tests

Test:

- Login
- Registration
- Product creation
- Cart operations
- Checkout
- Transaction history
- Reports
- Error states
- Network failures

### Important edge cases

```text
Quantity = 0
Negative price
Very large quantity
Expired/invalid token
Duplicate checkout request
Network timeout
Database failure
Unknown product ID
Unauthorized resource access
Concurrent updates
```

---

# 📊 Observability & Operations

For production, add:

- Structured application logs
- Error tracking
- Health checks
- API latency monitoring
- Database monitoring
- Uptime monitoring
- Alerting
- Automated backups
- Backup restoration testing

A healthy production system should allow you to answer:

> "What failed, when did it fail, which user was affected, and can we recover?"

---

# 🔄 CI/CD

A recommended GitHub Actions pipeline:

```text
Pull Request
     ↓
Build
     ↓
Unit Tests
     ↓
Integration Tests
     ↓
Static Analysis
     ↓
Security Checks
     ↓
Merge
     ↓
Deploy Backend
     ↓
Build Release Android
```

Keep deployment credentials in GitHub/hosting secrets — never inside the repository.

---

# 🏷️ Versioning

Use semantic versioning where practical:

```text
MAJOR.MINOR.PATCH
```

Example:

```text
1.0.0
1.0.1
1.1.0
2.0.0
```

Suggested meaning:

- **MAJOR** — breaking changes
- **MINOR** — new features
- **PATCH** — bug/security fixes

---

# 📦 Current APK

Current website build information:

| Property | Value |
|---|---|
| Version | 1.0 |
| Build | 1 |
| Android | 7.0+ |
| Architecture | Universal |
| Size | ~18.7 MB |
| Permissions | Internet |
| Package | `com.example.pos_system` |
| Distribution | Direct APK |
| Price | Free |

### SHA-256

```text
60985b00621109b1246ce3214fce4b72fa8763b6ce33272e24cb1c823921929d
```

> ⚠️ **Current build status:** The website currently describes the APK as a development/debug build. Do not use it with real customer or payment data until a properly signed release build, production backend, security review, and operational safeguards are in place.

---

# 🗺️ Roadmap

## ✅ Completed

- [x] Android POS application
- [x] Jetpack Compose UI
- [x] Authentication flow
- [x] Product catalog
- [x] Product creation
- [x] Billing/cart
- [x] Checkout flow
- [x] Transaction history
- [x] Sales reporting
- [x] Profile
- [x] Cloud-backed data
- [x] Password recovery workflow
- [x] Portfolio website

## 🚧 Production Hardening

- [ ] Replace `com.example.pos_system` with a production application ID
- [ ] Create signed release build
- [ ] Move all secrets to secure environment configuration
- [ ] Enforce HTTPS everywhere
- [ ] Implement/verify robust authentication
- [ ] Implement/verify role-based authorization
- [ ] Add server-side transaction validation
- [ ] Add idempotent checkout
- [ ] Add database indexes
- [ ] Configure backups
- [ ] Configure monitoring and alerting
- [ ] Add automated tests
- [ ] Add CI/CD
- [ ] Perform dependency/security scanning
- [ ] Add privacy policy and terms
- [ ] Add production support process

## 🔮 Future Features

- [ ] Inventory/stock management
- [ ] Low-stock alerts
- [ ] Barcode scanning
- [ ] Receipt printing
- [ ] PDF receipts
- [ ] Thermal printer support
- [ ] UPI/payment-gateway integration
- [ ] GST/tax configuration
- [ ] Discounts and coupons
- [ ] Multiple payment methods
- [ ] Returns/refunds
- [ ] Multiple cashiers
- [ ] Role-based access control
- [ ] Multiple shops/branches
- [ ] Offline-first billing
- [ ] Background synchronization
- [ ] Conflict resolution
- [ ] Advanced analytics
- [ ] Web-based admin dashboard
- [ ] Cloud-based backups
- [ ] Play Store release

---

# 🧠 Production Design Principles

The long-term goal is not simply to make the application "work."

The system should be:

### Reliable
A failed network request should not accidentally create two sales.

### Secure
Users should only access resources they are authorized to access.

### Consistent
The server and database should remain the source of truth for business-critical data.

### Observable
Errors should be detectable and diagnosable.

### Scalable
The architecture should support more products, users, shops, and transactions without redesigning the entire system.

### Maintainable
Features should be separated into clear UI, business, API, and persistence layers.

---

# 🤝 Contributing

Contributions, bug reports, and suggestions are welcome.

### Development workflow

```bash
git checkout -b feature/your-feature
```

Make your changes, test them, and create a pull request.

Recommended commit style:

```text
feat: add barcode scanning
fix: prevent duplicate transactions
refactor: improve product repository
test: add checkout service tests
docs: update deployment guide
```

---

# 🐛 Reporting Issues

When reporting a bug, include:

- Android version
- App version/build
- Steps to reproduce
- Expected behavior
- Actual behavior
- Relevant logs/screenshots
- Whether the issue occurs on Wi-Fi/mobile data

Never include passwords, access tokens, API keys, or other secrets in an issue.

---

# 📄 License

This project is licensed under the **MIT License** unless a different license is specified in the repository.

---

# 👨‍💻 Author

**Akshay Sharma**

> Full-Stack / Android Developer

- 🌐 Portfolio: `https://pos-app-beta-seven.vercel.app/`
- 💻 GitHub: `YOUR_GITHUB_URL`
- 🔗 LinkedIn: `YOUR_LINKEDIN_URL`
- 📧 Email: `YOUR_EMAIL`

---

# ⭐ Support the Project

If you find this project useful:

- ⭐ Star the repository
- 🐛 Report bugs
- 💡 Suggest features
- 🔀 Submit pull requests
- 📢 Share the project

---

<p align="center">

### 🧾 POS System

**Simple billing. Cloud-backed data. Built to become production-ready.**

</p>
