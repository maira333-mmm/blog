<div align="center">

<img width="100%" src="https://capsule-render.vercel.app/api?type=waving&height=210&color=0:1E3A5F,50:2563EB,100:60A5FA&text=SENA*%20Blog&fontColor=ffffff&fontSize=50&fontAlignY=38&desc=PHP%20%7C%20MySQL%20%7C%20Blog%20CMS&descAlignY=60&animation=fadeIn" alt="SENA* Blog Header" />

<br>

<img src="https://readme-typing-svg.demolab.com?font=Inter&weight=600&size=20&duration=2800&pause=700&color=2563EB&center=true&vCenter=true&repeat=true&width=700&height=52&lines=Full-Stack+PHP+Blog+Application.;Featured+Posts+%7C+Categories+%7C+Search.;User+Authentication+%7C+Admin+Dashboard.;Clean+%26+Responsive+Design." alt="Typing Animation" />

<br><br>

A complete **PHP Blog Application** with user authentication, category management, search functionality, and an admin dashboard. Built with **PHP, MySQL, HTML, CSS, and JavaScript**.

<br>

<a href="https://github.com/maira333-mmm/blog">
  <img src="https://img.shields.io/badge/📂_SOURCE_CODE-181717?style=for-the-badge&logo=github&logoColor=white" alt="Source Code"/>
</a>

<a href="https://github.com/maira333-mmm/blog/commits/main">
  <img src="https://img.shields.io/github/last-commit/maira333-mmm/blog?style=for-the-badge&label=LAST%20UPDATE" alt="Last Update"/>
</a>

<br><br>

<img src="https://img.shields.io/badge/PHP-777BB4?style=flat-square&logo=php&logoColor=white"/>
<img src="https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=mysql&logoColor=white"/>
<img src="https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white"/>
<img src="https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white"/>
<img src="https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black"/>
<img src="https://img.shields.io/badge/Responsive-00C853?style=flat-square"/>

</div>

---

# 📋 Table of Contents

- 📖 About
- ✨ Features
- 📁 Project Structure
- 🗄️ Database Schema
- 🚀 Getting Started
- 🔧 Installation
- 💻 Usage Guide
- 📑 Pages Overview
- 🔐 Authentication System
- 🎨 UI/UX Design
- 📊 Workflow Diagram
- 🛠 Technologies Used
- 🌍 Browser Compatibility
- 🤝 Contributing
- 📬 Contact
- 📄 License
- 🙏 Acknowledgements

---

# 📖 About

**SENA*** is a feature-rich **PHP Blog Application** that allows users to read, search, and interact with blog posts. The system features a clean, responsive design with user authentication, category management, and an admin dashboard for content management.

## 🎯 Key Highlights

- ✅ **Featured Posts** - Highlight important posts on homepage
- ✅ **Category System** - Organize posts by categories
- ✅ **Search Functionality** - Find posts by title
- ✅ **User Authentication** - Sign up, Sign in, Logout
- ✅ **Admin Dashboard** - Create, edit, delete posts
- ✅ **Role-Based Access** - Admin and Regular users
- ✅ **Responsive Design** - Works on all devices
- ✅ **Time Ago System** - Human-readable post timestamps

---

# ✨ Features

| Feature | Description |
|---------|-------------|
| 📝 **Blog Posts** | Create, read, update, delete posts |
| ⭐ **Featured Posts** | Highlight important content on homepage |
| 📂 **Categories** | Organize posts with categories |
| 🔍 **Search** | Search posts by title |
| 🔐 **Authentication** | Sign up, Sign in, Logout |
| 👑 **Admin Dashboard** | Manage posts and users |
| 👤 **User Profiles** | Avatar and user information |
| 📱 **Responsive** | Mobile-friendly design |
| 🕐 **Time Ago** | Human-readable timestamps |
| 🎨 **Modern UI** | Clean, professional design |

---

# 📁 Project Structure

```text
php-blog/
│
├── README.md
├── index.php                        # Homepage with featured posts
├── blog.php                         # All posts listing
├── post.php                         # Single post view
├── category_posts.php               # Posts by category
├── search.php                       # Search results
├── about.php                        # About page
├── services.php                     # Services page
├── contact.php                      # Contact page
├── signin.php                       # Login page
├── signup.php                       # Registration page
├── signin_logic.php                 # Login logic
├── signup_logic.php                 # Registration logic
├── logout.php                       # Logout handler
│
├── admin/                           # Admin Dashboard
│   ├── index.php                    # Admin dashboard
│   ├── add-post.php                 # Create new post
│   ├── edit-post.php                # Edit post
│   ├── delete-post.php              # Delete post
│   ├── manage-users.php             # User management
│   ├── add-user.php                 # Add user
│   ├── edit-user.php                # Edit user
│   └── delete-user.php              # Delete user
│
├── partials/
│   ├── header.php                   # Header with navigation
│   └── footer.php                   # Footer section
│
├── config/
│   ├── constants.php                # Application constants
│   └── database.php                 # Database connection
│
├── css/
│   └── style.css                    # Custom styles
│
├── js/
│   └── main.js                      # JavaScript functionality
│
├── images/                          # Uploaded images
│   ├── post_thumbnails/
│   └── avatars/
│
## 🗄️ Database Schema

### 👤 Users Table

```sql
CREATE TABLE users (
    id INT PRIMARY KEY AUTO_INCREMENT,
    firstname VARCHAR(50) NOT NULL,
    lastname VARCHAR(50) NOT NULL,
    username VARCHAR(50) UNIQUE NOT NULL,
    email VARCHAR(100) UNIQUE NOT NULL,
    password VARCHAR(255) NOT NULL,
    avatar VARCHAR(255),
    is_admin BOOLEAN DEFAULT 0,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

---

### 📂 Categories Table

```sql
CREATE TABLE categories (
    id INT PRIMARY KEY AUTO_INCREMENT,
    title VARCHAR(100) NOT NULL,
    description TEXT,
    created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

---

### 📝 Posts Table

```sql
CREATE TABLE posts (
    id INT PRIMARY KEY AUTO_INCREMENT,
    title VARCHAR(255) NOT NULL,
    body TEXT NOT NULL,
    thumbnail VARCHAR(255),
    category_id INT NOT NULL,
    author_id INT NOT NULL,
    is_featured BOOLEAN DEFAULT 0,
    date_time TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (category_id) REFERENCES categories(id) ON DELETE CASCADE,
    FOREIGN KEY (author_id) REFERENCES users(id) ON DELETE CASCADE
);
```

---

# 🚀 Getting Started

## 📋 Requirements

- 🐘 PHP 7.4+
- 🗄️ MySQL 5.7+
- 🌐 Apache / Nginx
- 🖥️ XAMPP / WAMP / MAMP (Recommended)

---

# 🔧 Installation

## 1️⃣ Clone Repository

```bash
git clone https://github.com/maira333-mmm/php-blog.git
cd php-blog
```

---

## 2️⃣ Setup Database

Create a database named **blog_db**.

```sql
CREATE DATABASE blog_db;
USE blog_db;
```

Run the SQL tables shown above.

---

## 3️⃣ Configure Database Connection

Update:

```
config/database.php
```

```php
<?php

$host = "localhost";
$user = "root";
$password = "";
$database = "blog_db";

$connection = new mysqli($host,$user,$password,$database);

if($connection->connect_error){
    die("Connection Failed : ".$connection->connect_error);
}

?>
```

---

## 4️⃣ Configure Constants

Update

```
config/constants.php
```

```php
<?php

session_start();

define("ROOT_URL","http://localhost/php-blog/");

define("DB_HOST","localhost");
define("DB_USER","root");
define("DB_PASS","");
define("DB_NAME","blog_db");

require_once "database.php";

?>
```

---

## 5️⃣ Run Project

### XAMPP

Place project inside

```
htdocs/
```

Start

- Apache
- MySQL

Visit

```
http://localhost/php-blog/
```

---

### WAMP

Place project inside

```
www/
```

Visit

```
http://localhost/php-blog/
```

---

# 💻 Usage Guide

## 👤 User Registration

- Open **Sign Up**
- Enter First Name
- Enter Last Name
- Enter Username
- Enter Email
- Enter Password
- Confirm Password
- Upload Avatar (Optional)
- Click **Register**

---

## 🔐 User Login

- Open **Sign In**
- Enter Username or Email
- Enter Password
- Click Login

---

## 📰 Reading Blog Posts

### Browse Posts

- Visit Blog page
- View all published posts
- Sort by newest

### Featured Posts

Featured articles appear on the Home page.

### Category Filter

Select a category to display related posts.

### Single Post

Open any article to read complete content.

---

## 🔍 Search Posts

- Enter keywords
- Click Search
- View matching articles

---

## 👨‍💻 Admin Dashboard

### Add Post

- Title
- Description
- Category
- Thumbnail
- Featured Option

Click **Publish**

---

### Edit Post

Modify article information.

---

### Delete Post

Remove article permanently.

---

# 📑 Pages Overview

| Page | URL | Description |
|------|------|-------------|
| 🏠 Home | / | Featured & Recent Posts |
| 📰 Blog | blog.php | All Blog Posts |
| 📄 Single Post | post.php | Post Details |
| 📂 Categories | category_posts.php | Category Posts |
| 🔍 Search | search.php | Search Results |
| ℹ️ About | about.php | About Website |
| 🛠 Services | services.php | Services |
| 🔐 Sign In | signin.php | Login |
| 📝 Sign Up | signup.php | Register |
| ⚙️ Admin | admin/ | Dashboard |

---

# 🔐 Authentication

## Registration

```php
$hashed_password = password_hash($password,PASSWORD_DEFAULT);

$query="INSERT INTO users(firstname,lastname,username,email,password,avatar)
VALUES(?,?,?,?,?,?)";
```

---

## Login

```php
$user=mysqli_fetch_assoc($result);

if(password_verify($password,$user['password'])){

$_SESSION['user-id']=$user['id'];

if($user['is_admin']){
$_SESSION['user_is_admin']=true;
}

header("Location: ".ROOT_URL."admin/");

}
```

---

## Session

```php
if(isset($_SESSION['user-id'])){

// Logged In

}else{

// Guest

}
```

---

# 🏗️ Website Workflow

```text
Visitor
   │
   ▼
Homepage
   │
   ▼
Browse Posts
   │
   ▼
Open Article
   │
   ▼
Search / Category
   │
   ▼
Login
   │
   ▼
Dashboard
   │
   ▼
Add / Edit / Delete Posts
```

---

# 🎨 UI / UX Design

## 🎨 Color Palette

| Color | Hex | Usage |
|--------|------|-------|
| 🔵 Primary Blue | #2563EB | Buttons |
| 🌑 Dark Blue | #1E3A5F | Header |
| 🟢 Success | #10B981 | Success Alerts |
| 🔴 Danger | #EF4444 | Errors |
| ⚪ White | #FFFFFF | Background |
| ⚫ Gray | #F3F4F6 | Cards |

---

## ✨ Features

- ✅ Responsive Layout
- ✅ Featured Posts
- ✅ Search Functionality
- ✅ Category Filtering
- ✅ Admin Dashboard
- ✅ User Authentication
- ✅ Avatar Upload
- ✅ Mobile Friendly

---

# 🛠 Technologies Used

| Technology | Purpose |
|------------|----------|
| PHP | Backend |
| MySQL | Database |
| HTML5 | Structure |
| CSS3 | Styling |
| JavaScript | Interactivity |
| Font Awesome | Icons |
| Unicons | Icons |
| XAMPP | Development |

---

# 🌐 Browser Compatibility

| Browser | Supported |
|----------|-----------|
| Chrome | ✅ |
| Firefox | ✅ |
| Edge | ✅ |
| Safari | ✅ |
| Opera | ✅ |
| Mobile Browsers | ✅ |

---

# 📁 Project Structure

```text
php-blog/
│
├── admin/
├── assets/
├── config/
│   ├── constants.php
│   └── database.php
├── images/
├── includes/
├── blog.php
├── post.php
├── category_posts.php
├── search.php
├── signin.php
├── signup.php
├── index.php
├── about.php
├── services.php
├── README.md
└── LICENSE
```

---

# 🤝 Contributing

```text
Fork Repository
      │
      ▼
Create Branch
      │
      ▼
Commit Changes
      │
      ▼
Push Branch
      │
      ▼
Open Pull Request
```

---

# 📬 Contact


<div align="center">

## 👩‍💻 Maira Alam

<a href="https://mail.google.com/mail/?view=cm&fs=1&to=maira.alam33@gmail.com">
  <img src="https://img.shields.io/badge/Gmail-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Gmail"/>
</a>

<a href="https://github.com/maira333-mmm">
<img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white"/>
</a>

<a href="https://www.linkedin.com/in/maira-a-48699630b/">
<img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white"/>
</a>

<a href="https://maira-alam-o2p20gi.gamma.site/">
<img src="https://img.shields.io/badge/Portfolio-2563EB?style=for-the-badge&logo=googlechrome&logoColor=white"/>
</a>

</div>

---


# 📄 License

Licensed under the **MIT License**.

---

# 🎯 Future Enhancements

| Feature | Description |
|----------|-------------|
| 💬 Comments | User Comments |
| ❤️ Likes | Like Articles |
| 📧 Email Notifications | Notify Subscribers |
| 📱 Mobile App | React Native |
| 🌍 Multi-language | Localization |
| 📊 Analytics | Post Statistics |
| 🏷 Tags | Multiple Tags |
| 🔔 Push Notifications | Browser Notifications |

---

# 🐛 Troubleshooting

<details>

<summary><b>❌ Database Connection Error</b></summary>

```php
define("DB_HOST","localhost");
define("DB_USER","root");
define("DB_PASS","");
define("DB_NAME","blog_db");
```

</details>

---

<details>

<summary><b>❌ Session Not Starting</b></summary>

```php
session_start();
```

Place it before any HTML output.

</details>

---

<details>

<summary><b>❌ Image Upload Failed</b></summary>

```bash
chmod -R 755 images/
chmod -R 755 admin/images/
```

Ensure folder permissions and upload paths are correct.

</details>

---

# 🙏 Acknowledgements

| Resource | Purpose |
|-----------|----------|
| Shields.io | Badges |
| GitHub | Repository Hosting |
| PHP Documentation | Backend Reference |
| MySQL Documentation | Database Reference |
| Font Awesome | Icons |
| Unicons | Icons |

---

<div align="center">

# ❤️ Built with PHP & MySQL

Made with 💙 by **Maira Alam**

⭐ If you found this project helpful, consider giving it a **Star**.

</div>
