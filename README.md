# Secure HRMS REST API

A production-ready Human Resource Management System (HRMS) REST API built using **Django**, **Django REST Framework**, and **JWT Authentication**. This project demonstrates enterprise-level API security, authentication, authorization, validation, logging, and best practices.

---

# Features

## Authentication
- JWT Login
- Access Token Generation
- Refresh Token Generation
- Refresh Access Token
- Secure Logout
- Token Blacklisting
- Change Password
- Forgot Password
- Reset Password

---

## Employee Management

- Employee CRUD
- Employee Profile API
- Profile Image Upload
- Employee Search
- Employee Filtering
- Ordering
- Pagination

---

## Department Management

- Department CRUD APIs

---

## Security

- JWT Authentication
- Refresh Token Flow
- Token Blacklisting
- Role-Based Authorization
- Object-Level Permissions
- API Rate Limiting
- Secure File Upload Validation
- Security Audit Logging
- Password Validation
- Input Validation
- Standard Error Responses

---

# Roles

- Admin
- HR
- Manager
- Employee

---

# Role Permissions

| Feature | Admin | HR | Manager | Employee |
|---------|:-----:|:--:|:-------:|:--------:|
| Employee CRUD | ✅ | ✅ | ❌ | ❌ |
| Department CRUD | ✅ | ✅ | ❌ | ❌ |
| View Dashboard | ✅ | ✅ | ✅ | ❌ |
| Reports | ✅ | ❌ | ❌ | ❌ |
| Own Profile | ✅ | ✅ | ✅ | ✅ |
| Other Employee Profile | ✅ | ✅ | ❌ | ❌ |

---

# API Modules

## Module 1

### JWT Authentication

- Login
- Refresh Token

Endpoints

```
POST /api/v1/auth/login/
POST /api/v1/auth/refresh/
```

---

## Module 2

### Logout

```
POST /api/v1/auth/logout/
```

Features

- Blacklist Refresh Token
- Prevent Token Reuse

---

## Module 3

### Change Password

```
POST /api/v1/auth/change-password/
```

Features

- Verify Current Password
- Validate New Password
- Hash Password
- Invalidate Refresh Tokens

---

## Module 4

### Forgot Password

```
POST /api/v1/auth/forgot-password/

POST /api/v1/auth/reset-password/
```

Features

- Secure Reset Token
- Token Expiry (15 Minutes)
- Password Reset

---

## Module 5

### API Authorization

Custom Permission Classes

- IsAdmin
- IsHR
- IsManager
- IsEmployee

---

## Module 6

### Object Level Permission

Employee can access only

```
GET /api/v1/profile/
```

Employee cannot access

```
GET /api/v1/employees/{id}/
```

---

## Module 7

### API Rate Limiting

| API | Limit |
|------|-------|
| Login | 5 Requests / Minute |
| Employee | 100 Requests / Minute |
| Reports | 20 Requests / Minute |

---

## Module 8

### Secure File Upload

Validation

- JPG
- JPEG
- PNG
- Maximum 2 MB

Blocked Files

- EXE
- ZIP
- JS
- BAT

---

## Module 9

### Request Validation

Employee ID

```
EMP00001
```

Validation

- Employee ID Format
- Unique Email
- Valid Email
- Phone (10 Digits)
- Positive Salary
- Joining Date Not Future

---

## Module 10

### Security Logging

Tracks

- Login Success
- Login Failure
- Password Change
- Password Reset
- Unauthorized Access
- Permission Denied
- Token Blacklisted

Stored Fields

- User
- IP Address
- Timestamp
- Action
- Status

---

## Module 11

### API Security Best Practices

- HTTPS Ready
- Strong Password Validation
- Secure Serializers
- Input Validation
- Standard Error Responses
- Prevent Information Leakage
- Authentication on Protected APIs
- Proper Permission Checks

---

## Module 12

### HRMS Secure API Platform

Includes

- Authentication APIs
- Employee APIs
- Department APIs
- Dashboard APIs
- Reports APIs
- Role-Based Authorization
- Object-Level Permissions
- Rate Limiting
- File Upload Validation
- Security Logging

---

# Project Structure

```
company_portal/

accounts/
│
├── authentication.py
├── permissions.py
├── serializers.py
├── services.py
├── security.py
├── validators.py
├── views.py
├── urls.py

employees/
departments/
dashboard/
reports/
logs/

config/

manage.py
requirements.txt
README.md
```

---

# Technologies Used

- Python
- Django
- Django REST Framework
- JWT Authentication
- PostgreSQL
- SimpleJWT
- Git
- GitHub

---

# Installation

Clone Repository

```bash
git clone <repository-url>
```

Move into Project

```bash
cd company_portal
```

Create Virtual Environment

```bash
python -m venv venv
```

Activate Virtual Environment

Windows

```bash
venv\Scripts\activate
```

Install Dependencies

```bash
pip install -r requirements.txt
```

Run Migrations

```bash
python manage.py makemigrations
python manage.py migrate
```

Run Server

```bash
python manage.py runserver
```

---

# Git Workflow

```bash
git checkout development

git pull origin development

git checkout -b feature/jwt-api-security

git add .

git commit -m "Implemented JWT API Security"

git push -u origin feature/jwt-api-security
```

---

# Future Improvements

- Email Notifications
- Celery + Redis
- Swagger Documentation
- Docker
- CI/CD Pipeline
- Unit Testing
- API Versioning

---

# Author

**Ritesh Kodshetti**

Python Developer

---

# License

This project is developed for learning and enterprise-level Django REST Framework security implementation.
