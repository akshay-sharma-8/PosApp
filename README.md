# 🧾 Smart Shop — Point of Sale (POS)

A full-stack Android POS application built to make billing and basic shop management simple.

The app allows shop owners/cashiers to manage products, create bills, record sales, and view transaction and sales information from one place.

🌐 **Project Website:** https://pos-app-beta-seven.vercel.app/

---

## ✨ Features

- 🔐 User registration and login
- 📧 OTP-based password recovery
- 📦 Add, edit, and manage products
- 🛒 Cart and billing system
- 💳 Checkout and payment flow
- 🧾 Transaction history
- 📊 Sales and financial reports
- 👤 User profile management
- ☁️ Data stored through a backend API

---

## 🛠️ Tech Stack

### Android
- **Kotlin**
- **Jetpack Compose**
- **Retrofit**
- **Coroutines**
- **MVVM**

### Backend
- **Spring Boot**
- **REST APIs**
- **Spring Security**
- **Spring Mail**
- **JPA / Hibernate**

### Database
- **MySQL**

### Deployment
- Android APK
- Spring Boot backend
- Cloud-hosted MySQL database
- Vercel for the project website

---

## 🏗️ How It Works

```text
Android App
     │
     │ REST API
     ▼
Spring Boot Backend
     │
     │ JPA / Hibernate
     ▼
MySQL Database
```

The Android application communicates with the Spring Boot backend using REST APIs. The backend handles authentication, business logic, and database operations.

---

## 📱 Main Screens

- Login
- Register
- Forgot Password
- Dashboard
- Products
- Add Product
- Billing
- Payment
- Transactions
- Reports
- Profile

---

## 🚀 Run Locally

### 1. Clone the project

```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPOSITORY.git
cd YOUR_REPOSITORY
```

### 2. Database

Create a MySQL database:

```sql
CREATE DATABASE pos_system;
```

Configure your database connection in the Spring Boot application:

```properties
spring.datasource.url=jdbc:mysql://localhost:3306/pos_system
spring.datasource.username=YOUR_USERNAME
spring.datasource.password=YOUR_PASSWORD
```

For production, keep database credentials and other secrets in environment variables instead of committing them to Git.

### 3. Start the backend

```bash
./mvnw spring-boot:run
```

### 4. Run the Android app

Open the Android project in **Android Studio**, sync Gradle, make sure the backend URL is configured, and run the application on an emulator or Android device.

---

## 🔒 Production Improvements

The current project is being developed with real-world deployment in mind. Before using it in a real shop, I plan to add/verify:

- Proper release signing
- Strong authentication and authorization
- Server-side bill validation
- Duplicate transaction protection
- Database backups
- API monitoring and error logging
- Automated testing
- CI/CD deployment
- Payment gateway integration
- Barcode scanning
- GST/tax support
- Inventory and stock management

---

## 🗺️ Roadmap

- [x] Authentication
- [x] Product management
- [x] Billing
- [x] Transactions
- [x] Reports
- [x] Password recovery
- [x] MySQL database
- [x] Android UI with Jetpack Compose
- [ ] Inventory management
- [ ] Barcode scanner
- [ ] GST support
- [ ] Receipt printing
- [ ] UPI/payment integration
- [ ] Production release

---

## 📦 Current Build

**Version:** 1.0  
**Platform:** Android  
**Minimum Android:** 7.0+  
**Package:** `com.example.pos_system`

### SHA-256

```text
60985b00621109b1246ce3214fce4b72fa8763b6ce33272e24cb1c823921929d
```

> The current APK is a development build. A properly signed release build should be used before production deployment.

---

## 👨‍💻 Author

**Akshay Sharma**

Full-Stack / Android Developer

- GitHub: `YOUR_GITHUB_URL`
- LinkedIn: `YOUR_LINKEDIN_URL`
- Email: `YOUR_EMAIL`

---

## ⭐ About the Project

I built this project to gain practical experience in **Android development, REST API design, backend development, database management, authentication, and deploying a complete full-stack application**.

If you like the project, feel free to ⭐ the repository.
