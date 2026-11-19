# 🍋 Little Lemon – Back-End Capstone Project

### Django REST Framework | MySQL | REST API

A back-end web application developed as part of the **Back-End Developer Capstone Project**. Little Lemon uses Django REST Framework and MySQL to manage menu items and table bookings through RESTful APIs, with token-based authentication and user management.

---

## 🚀 Tech Stack

| Technology | Purpose |
|---|---|
| Python | Core Programming Language |
| Django | Back-End Web Framework |
| Django REST Framework | REST API Development |
| MySQL | Relational Database |
| Djoser | User Authentication |
| Token Authentication | API Security |
| Insomnia | API Testing |

---

## ⚙️ Installation & Setup

Follow these steps to run the project locally.

### 1. Clone the Repository

```bash
git clone <your-repository-url>
cd <project-folder>
```

### 2. Create the MySQL Database

Open MySQL and execute:

```sql
CREATE DATABASE littlelemon;
```

### 3. Configure Database Settings

Open `littlelemon/settings.py` and update the `DATABASES` configuration with your MySQL credentials.

```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.mysql',
        'NAME': 'littlelemon',
        'USER': 'your_mysql_username',
        'PASSWORD': 'your_mysql_password',
        'HOST': 'localhost',
        'PORT': '3306',
    }
}
```

### 4. Install Dependencies

Open the project in VS Code and execute the following commands in the terminal:

```bash
pipenv install
pipenv shell
```

### 5. Apply Database Migrations

```bash
python manage.py makemigrations
python manage.py migrate
```

### 6. Start the Development Server

```bash
python manage.py runserver
```

The application will be available at:

**http://127.0.0.1:8000/**

---

## 🔗 API Endpoints

Base URL: `http://127.0.0.1:8000`

### 1. Menu Management

| Method | Endpoint | Description | Authentication |
|---|---|---|---|
| GET | `/api/menu/` | Retrieve all menu items | Not required |
| POST | `/api/menu/` | Create a menu item | Required |
| GET | `/api/menu/1/` | Retrieve a specific item | Not required |
| PUT | `/api/menu/1/` | Update a menu item | Required |
| PATCH | `/api/menu/1/` | Partially update an item | Required |
| DELETE | `/api/menu/1/` | Delete a menu item | Required |

### 2. Booking Management

| Method | Endpoint | Description | Authentication |
|---|---|---|---|
| GET | `/api/bookings/` | Retrieve all bookings | Required |
| POST | `/api/bookings/` | Create a booking | Required |
| GET | `/api/bookings/1/` | Retrieve a specific booking | Required |
| PUT | `/api/bookings/1/` | Update a booking | Required |
| PATCH | `/api/bookings/1/` | Partially update a booking | Required |
| DELETE | `/api/bookings/1/` | Delete a booking | Required |

### 3. Authentication & User Management

| Method | Endpoint | Description |
|---|---|---|
| POST | `/auth/users/` | Register a new user |
| POST | `/auth/token/login/` | Login and obtain authentication token |
| POST | `/auth/token/logout/` | Logout and invalidate token |
| GET | `/auth/users/me/` | Retrieve current user details |

### 4. Other Pages

| Endpoint | Description |
|---|---|
| `/` | Static HTML home page |
| `/admin/` | Django Administration Panel |

---

## 🧪 API Testing with Insomnia

Use [Insomnia](https://insomnia.rest/) to test the REST API endpoints.

### Step 1: Register a New User

**POST** `/auth/users/`

Request Body (JSON):

```json
{
    "username": "testuser",
    "password": "Str0ngPass!234"
}
```

### Step 2: Login and Generate Authentication Token

**POST** `/auth/token/login/`

Request Body (JSON):

```json
{
    "username": "testuser",
    "password": "Str0ngPass!234"
}
```

Copy the `auth_token` received in the response.

### Step 3: Configure Authentication

For protected API requests, add the following HTTP header:

```http
Authorization: Token <auth_token>
```

### Step 4: Create a Menu Item

**POST** `/api/menu/`

Request Body (JSON):

```json
{
    "title": "Greek Salad",
    "price": "12.99",
    "inventory": 20
}
```

### Step 5: Create a Table Booking

**POST** `/api/bookings/`

Request Body (JSON):

```json
{
    "name": "Jane",
    "no_of_guests": 4,
    "booking_date": "2026-12-01T19:00:00Z"
}
```

### Step 6: Verify the Data

Send the following GET requests:

- `GET /api/menu/` – View all menu items.
- `GET /api/bookings/` – View all bookings.

You should now be able to see the newly created records.

---

## 🔐 Authentication

The project uses **Token-Based Authentication** to secure protected API endpoints.

- User registration through Djoser.
- Login generates an authentication token.
- Protected endpoints require a valid token.
- Logout invalidates the current authentication token.

---

## ✅ Running Unit Tests

To execute the project's test suite, run:

```bash
python manage.py test
```

Django will automatically discover and execute the available test cases.

---

## 📁 Project Highlights

- RESTful API development using Django REST Framework.
- MySQL database integration.
- Menu item creation, retrieval, updating, and deletion.
- Table booking management.
- User registration and token-based authentication.
- API testing using Insomnia.
- Unit testing using Django's testing framework.

---

## 👨‍💻 Project Information

**Project:** Little Lemon – Back-End Capstone  
**Framework:** Django REST Framework  
**Database:** MySQL  
**Development Environment:** Visual Studio Code

---

⭐ If you found this project interesting, feel free to explore the repository!
