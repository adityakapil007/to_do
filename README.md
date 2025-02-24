# Django Todo REST API

A robust RESTful API built with Django REST Framework for managing todo tasks with user authentication.

## Features

- 🔐 JWT Authentication
- ✨ CRUD Operations for Todo Items
- 👤 User Registration and Authentication
- 📝 Todo Status Management
- 📅 Due Date Tracking
- 🔄 Task Status Updates

## Tech Stack

- Django 5.0
- Django REST Framework 3.14.0
- PostgreSQL
- JWT Authentication
- Python 3.10+

## Prerequisites

- Python 3.10 or higher
- PostgreSQL
- pip (Python package installer)

## Installation

1. **Clone the repository**
```bash
git clone https://github.com/adityakapil007/to_do.git
cd todo_project
```

2. **Create a virtual environment**
```bash
python -m venv venv

# Windows
venv\Scripts\activate

# Linux/MacOS
source venv/bin/activate
```

3. **Install dependencies**
```bash
pip install -r requirements.txt
```

4. **Configure PostgreSQL**
- Install PostgreSQL
- Create a database named 'todo_db'
```sql
CREATE DATABASE todo_db;
```

5. **Update database configurations**
- Navigate to `todo_project/settings.py`
- Update database settings:
```python
DATABASES = {
    'default': {
        'ENGINE': 'django.db.backends.postgresql',
        'NAME': 'todo_db',
        'USER': 'postgres',
        'PASSWORD': 'your_password',
        'HOST': 'localhost',
        'PORT': '5432',
    }
}
```

6. **Apply migrations**
```bash
python manage.py makemigrations
python manage.py migrate
```

7. **Create superuser (Optional)**
```bash
python manage.py createsuperuser
```

8. **Run the development server**
```bash
python manage.py runserver
```

## API Endpoints

### Authentication
- `POST /api/auth/register/` - Register a new user
- `POST /api/auth/login/` - Login user
- `POST /api/auth/refresh/` - Refresh JWT token

### Todo Operations
- `GET /api/todos/` - List all todos
- `POST /api/todos/` - Create a new todo
- `GET /api/todos/{id}/` - Retrieve a specific todo
- `PUT /api/todos/{id}/` - Update a specific todo
- `DELETE /api/todos/{id}/` - Delete a specific todo

## API Usage

### Registration
```bash
curl -X POST http://localhost:8000/api/auth/register/ \
    -H "Content-Type: application/json" \
    -d '{"username": "user1", "password": "pass123", "email": "user1@example.com"}'
```

### Login
```bash
curl -X POST http://localhost:8000/api/auth/login/ \
    -H "Content-Type: application/json" \
    -d '{"username": "user1", "password": "pass123"}'
```

### Create Todo
```bash
curl -X POST http://localhost:8000/api/todos/ \
    -H "Authorization: Bearer <your_token>" \
    -H "Content-Type: application/json" \
    -d '{"title": "Complete Project", "description": "Finish the todo app", "due_date": "2024-01-20"}'
```

## Project Structure
```
todo_project/
│
├── todo_project/          # Project directory
│   ├── __init__.py
│   ├── settings.py        # Project settings
│   ├── urls.py           # Project URLs
│   ├── asgi.py
│   └── wsgi.py
│
├── todo/                  # App directory
│   ├── __init__.py
│   ├── admin.py          # Admin configuration
│   ├── apps.py           # App configuration
│   ├── models.py         # Database models
│   ├── serializers.py    # API serializers
│   ├── views.py          # API views
│   ├── urls.py           # App URLs
│   └── migrations/       # Database migrations
│
├── manage.py             # Django management script
├── requirements.txt      # Project dependencies
└── README.md            # Project documentation
```

## Running Tests
```bash
python manage.py test
```

## Contributing
1. Fork the repository
2. Create your feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## License
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Author
Arnim Taliyan - [Your GitHub Profile](https://github.com/ArnimTaliyan)

## Acknowledgments
- Django Documentation
- Django REST Framework
- PostgreSQL Documentation