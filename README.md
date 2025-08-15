# Django User Registration & Login (Integrated Project)

This is a single Django project that integrates **user registration** and **login/logout** with redirects and a protected dashboard.

## Features
- Register with username, email, and password (email uniqueness validated)
- Log in / Log out (uses Django auth views)
- Redirect to dashboard after login
- Auth-protected `dashboard/` route
- Messages for success/errors
- Simple styling using a global CSS file

## Project Structure
```
django_auth_project/
├── accounts/
│   ├── templates/
│   │   ├── accounts/
│   │   │   ├── dashboard.html
│   │   │   └── register.html
│   │   └── registration/
│   │       └── login.html
│   ├── __init__.py
│   ├── admin.py
│   ├── apps.py
│   ├── forms.py
│   ├── models.py
│   ├── urls.py
│   └── views.py
├── django_auth_project/
│   ├── __init__.py
│   ├── asgi.py
│   ├── settings.py
│   ├── urls.py
│   └── wsgi.py
├── static/
│   └── css/
│       └── style.css
├── manage.py
├── requirements.txt
└── README.md
```

## Quickstart

1. Create and activate a virtualenv:
   ```bash
   python -m venv venv
   # Windows: venv\Scripts\activate
   # macOS/Linux:
   source venv/bin/activate
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Run migrations:
   ```bash
   python manage.py migrate
   ```

4. (Optional) Create a superuser for Django admin:
   ```bash
   python manage.py createsuperuser
   ```

5. Start the development server:
   ```bash
   python manage.py runserver
   ```

6. Open the app:
   - Registration: `http://127.0.0.1:8000/accounts/register/`
   - Login: `http://127.0.0.1:8000/accounts/login/`
   - Dashboard (requires auth): `http://127.0.0.1:8000/accounts/dashboard/`

## Notes
- Default timezone set to `Asia/Kolkata` in `settings.py`.
- `LOGIN_REDIRECT_URL` points to `dashboard`. `LOGOUT_REDIRECT_URL` and `LOGIN_URL` are also configured.
- Uses SQLite by default; switch `DATABASES` in `settings.py` if needed.
