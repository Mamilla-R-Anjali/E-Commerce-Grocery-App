# E-Commerce Project (PHP & MySQL)

## Project Overview
This is a simple e-commerce web application built using PHP and MySQL. It includes user authentication, product management, shopping cart system, and an admin panel.

## Tech Stack
- PHP (Server-side logic)
- MySQL (Database)
- HTML5 (Frontend structure)
- CSS3 (Styling)
- PDO (Database connectivity)
- PHP Sessions (Authentication & user management)

## Local Setup Links
http://localhost/ecommerce/index.php  
http://localhost/ecommerce/login.php  
http://localhost/ecommerce/register.php  
http://localhost/ecommerce/cart.php  

http://localhost/ecommerce/admin/login.php  
http://localhost/ecommerce/admin/dashboard.php  
http://localhost/ecommerce/admin/add_product.php  
http://localhost/ecommerce/admin/manage_products.php  

## Features

User Features:
- User registration and login
- Product listing
- Add to cart
- Update quantity in cart
- Remove items from cart
- View total cost
- Logout

Admin Features:
- Admin login system
- Add new products
- Manage products (edit/delete/view)
- Upload product images
- Admin dashboard

## Security Features
- Password hashing using password_hash()
- Password verification using password_verify()
- Session-based authentication
- Role-based access control (Admin/User)
- Protected pages using session checks

## Database Setup

### Create Database
```sql
CREATE DATABASE ecommerce;
```

---

### Users Table
```sql
CREATE TABLE users (
    id INT AUTO_INCREMENT PRIMARY KEY,
    username VARCHAR(50) NOT NULL,
    email VARCHAR(100) NOT NULL UNIQUE,
    password VARCHAR(255) NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    role ENUM('user', 'admin') DEFAULT 'user'
);
```

---

### Products Table
```sql
CREATE TABLE products (
    id INT AUTO_INCREMENT PRIMARY KEY,
    name VARCHAR(255) NOT NULL,
    price DECIMAL(10, 2) NOT NULL,
    description TEXT,
    image VARCHAR(255),
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

---

### Cart Table
```sql
CREATE TABLE cart (
    id INT AUTO_INCREMENT PRIMARY KEY,
    user_id INT NOT NULL,
    product_id INT NOT NULL,
    quantity INT NOT NULL,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    updated_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP ON UPDATE CURRENT_TIMESTAMP
);
```
## Setup Instructions
1. Install XAMPP/WAMP
2. Place project in htdocs/ecommerce
3. Start Apache and MySQL
4. Import database in phpMyAdmin
5. Open:
http://localhost/ecommerce/index.php

## Login Flow
User: Register → Login → Add to Cart → Checkout  
Admin: Login → Dashboard → Manage Products

## Future Improvements
- Payment gateway integration
- Product search & filters
- Order history system
- Better UI with JavaScript
- Email verification
