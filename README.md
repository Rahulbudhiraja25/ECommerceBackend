# 🛒 E-Commerce Backend

[![Java](https://img.shields.io/badge/Java-17-orange)](https://www.java.com/)
[![Spring Boot](https://img.shields.io/badge/Spring%20Boot-3.2.2-brightgreen)](https://spring.io/projects/spring-boot)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-14-blue)](https://www.postgresql.org/)
[![License](https://img.shields.io/badge/License-MIT-green)](LICENSE)

A **scalable E-commerce backend** built with **Java Spring Boot** and **PostgreSQL**, featuring **user authentication, product management, cart operations, and order processing**. Fully modular and deployment-ready.

---

## 📌 Table of Contents

* [Features](#features)
* [Tech Stack](#tech-stack)
* [Database Schema](#database-schema)
* [Setup Instructions](#setup-instructions)
* [API Endpoints](#api-endpoints)
* [Learning Outcomes](#learning-outcomes)
* [Contributing](#contributing)
* [License](#license)

---

## 🛠 Features

### **User Management**

* User registration & login
* JWT-based authentication
* Roles: `USER` & `ADMIN`

### **Product Management**

* Add, update, delete products (Admin only)
* View all products or search by name/category

### **Cart System**

* Add products to cart
* View, update, or remove cart items

### **Order Management**

* Place orders from cart
* View order history
* Update order status (Admin only)

### **Optional Enhancements**

* Product reviews & ratings
* Email notifications
* Payment simulation
* File uploads for product images
* Pagination, sorting, and caching with Redis

---

## 🧰 Tech Stack

| Layer         | Technology                    |
| ------------- | ----------------------------- |
| Backend       | Java 17+, Spring Boot         |
| Database      | PostgreSQL                    |
| ORM           | Spring Data JPA (Hibernate)   |
| Auth          | Spring Security + JWT         |
| Testing       | JUnit, Mockito                |
| Documentation | Swagger/OpenAPI (optional)    |
| Deployment    | Docker, AWS/Render (optional) |

---

## 🗄 Database Schema (Simplified)

```
User        : id, name, email, password, role
Product     : id, name, description, price, stock, category
CartItem    : id, user_id, product_id, quantity
Order       : id, user_id, total_price, status, created_at
OrderItem   : id, order_id, product_id, quantity, price
```

---

## ⚙️ Setup Instructions

1. **Clone the repository**

```bash
git clone https://github.com/yourusername/ecommerce-backend.git
cd ecommerce-backend
```

2. **Configure PostgreSQL**

* Create database `ecommerce`
* Update `application.properties`:

```properties
spring.datasource.url=jdbc:postgresql://localhost:5432/ecommerce
spring.datasource.username=your_username
spring.datasource.password=your_password
```

3. **Build & Run**

```bash
mvn clean install
mvn spring-boot:run
```

4. **Access API**

* Base URL: `http://localhost:8080/api`
* Swagger UI (if enabled): `http://localhost:8080/swagger-ui.html`

---

## 📡 API Endpoints

### Auth

```
POST /api/auth/register
POST /api/auth/login
GET  /api/users/me
```

### Products

```
POST /api/products        (admin)
PUT  /api/products/{id}   (admin)
DELETE /api/products/{id} (admin)
GET  /api/products
GET  /api/products/{id}
```

### Cart

```
POST   /api/cart/add
GET    /api/cart
DELETE /api/cart/{productId}
```

### Orders

```
POST /api/orders
GET  /api/orders
GET  /api/orders/{id}
PUT  /api/orders/{id}/status  (admin)
```

---

## 🎯 Learning Outcomes

* Build REST APIs with Spring Boot
* Implement JWT authentication & authorization
* Design relational database schemas & JPA mappings
* Handle exceptions & input validation
* Structure a production-ready backend project

---

## 🤝 Contributing

Contributions are welcome!

1. Fork the repo
2. Create a feature branch
3. Submit a pull request

---

## 📝 License

This project is licensed under the **MIT License**.
