 # Django E-Commerce Shop

A full-stack e-commerce application built with **Django**, **Django REST Framework**, and **Vue.js**.

The project provides a reusable e-commerce backend with REST API endpoints, custom shopping cart functionality, a Vue.js frontend, Docker support, and application monitoring using Grafana and Loki.

## Tech Stack

### Backend

* Python
* Django 3.x
* Django REST Framework
* Django ORM

### Frontend

* Vue.js 2.x
* HTML
* Stylus

### DevOps & Monitoring

* Docker
* Docker Compose
* Grafana 8.x
* Loki 2.x

---

## Features

### Shopping Cart

Custom shopping cart functionality allows products to be added, updated, removed, and tracked throughout the shopping session.

### REST API

The backend exposes API endpoints using **Django REST Framework**, separating application logic from the frontend and allowing the application to be extended or integrated with other clients.

### DRF ViewSets

Django REST Framework ViewSets are used to organize API operations and reduce duplicated backend logic.

### Vue.js Frontend

The frontend is built separately using **Vue.js**, consuming data provided by the Django REST API.

### Django Admin

Django's built-in administration interface can be used to manage application data.

### Fixtures

Development data can be loaded using Django fixtures, making it easier to quickly populate the application for development and testing.

### Docker Support

The application includes Docker configuration for running the project in containers.

### Logging & Monitoring

Grafana and Loki are included in the project's monitoring stack for viewing and analyzing application logs.

---

## Project Structure

```text
ecommerce_shop/
│
├── webshop/                 # Django backend
│   ├── manage.py
│   ├── requirements.txt
│   ├── fixtures/
│   │   └── data.json
│   └── .env.template
│
├── django_frontend/         # Vue.js frontend
│
├── docker-compose.yml       # Docker Compose configuration
│
└── README.md
```

> The exact directory structure may vary depending on the version of the project.

---

## Getting Started

### Prerequisites

Make sure the following are installed:

* Python 3
* pip
* Node.js / npm
* Git
* Docker *(optional)*

---

## Installation

### 1. Clone the Repository

```bash
git clone https://github.com/vadimbushtruk/ecommerce_shop.git
cd ecommerce_shop
```

### 2. Create a Virtual Environment

```bash
python -m venv venv
```

Activate the environment.

**Windows:**

```bash
venv\Scripts\activate
```

**macOS / Linux:**

```bash
source venv/bin/activate
```

### 3. Install Backend Dependencies

Navigate to the Django backend:

```bash
cd webshop
```

Install the required Python packages:

```bash
pip install -r requirements.txt
```

---

## Environment Variables

The project includes an environment template:

```text
webshop/.env.template
```

Create your local `.env` file from the template.

**macOS / Linux:**

```bash
cp .env.template .env
```

**Windows:**

```bash
copy .env.template .env
```

Update the values inside `.env` for your local environment.

### Generate a Django Secret Key

You can generate a new Django secret key using:

```bash
python manage.py shell
```

Then:

```python
from django.core.management.utils import get_random_secret_key

print(get_random_secret_key())
```

Copy the generated key into the appropriate variable in your `.env` file.

**Never commit your real secret key or `.env` file to Git.**

---

## Database Setup

Create and apply database migrations:

```bash
python manage.py makemigrations
python manage.py migrate
```

---

## Create an Admin User

Create a Django superuser:

```bash
python manage.py createsuperuser
```

Follow the prompts to create your local administrator account.

---

## Load Development Data

The project contains fixture data that can be loaded with:

```bash
python manage.py loaddata fixtures/data.json
```

This can be used to quickly populate the application for development and testing.

---

## Running the Backend

Start the Django development server:

```bash
python manage.py runserver
```

By default, Django will start the development server on port `8000`.

---

## Frontend Setup

The frontend is located in:

```text
django_frontend/
```

Navigate to the directory:

```bash
cd ../django_frontend
```

Follow the frontend-specific instructions provided in that directory to install the required dependencies and start the Vue.js development server.

---

## Running with Docker

The project can also be started using Docker Compose.

Make sure the required environment variables are configured and database migrations have been applied.

Then run:

```bash
docker-compose up -d
```

To stop the containers:

```bash
docker-compose down
```

---

## Development

When making backend model changes, create and apply new migrations:

```bash
python manage.py makemigrations
python manage.py migrate
```

Run the Django development server:

```bash
python manage.py runserver
```

For frontend development, run the Vue.js application separately from the `django_frontend` directory.

---

## Monitoring

The project uses:

* **Grafana** for monitoring and visualization
* **Loki** for log aggregation

These services can be run as part of the project's containerized environment when configured through Docker Compose.

---

## Security

Sensitive configuration should be stored in environment variables rather than committed directly to the repository.

Do not commit:

```text
.env
```

Make sure `.env` is included in `.gitignore`.

Production deployments should also use:

* A unique Django `SECRET_KEY`
* `DEBUG=False`
* Proper `ALLOWED_HOSTS`
* Secure database credentials
* HTTPS
* Production-ready server configuration

---

## Future Improvements

Potential improvements to the project include:

* Automated backend testing
* API documentation with Swagger/OpenAPI
* Improved frontend error handling
* CI/CD pipeline
* Expanded product filtering and search
* Improved deployment configuration

---

## Author

**Vadim Bushtruk**

GitHub: `vadimbushtruk`

---

## License

This project is intended for educational and portfolio purposes.
