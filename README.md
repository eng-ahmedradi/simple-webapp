# Simple Web Application

A lightweight Python Flask web application for DevOps and containerization demonstration.

## Overview

This is a simple web application built with **Python Flask** and **MySQL** database. It demonstrates fundamental concepts of multi-tier application development and serves as a reference implementation for DevOps training, particularly for containerization, orchestration, and infrastructure automation.

## Technologies

- **Python 3** — Programming language
- **Flask** — Web framework
- **MySQL** — Relational database
- **Docker** — Containerization (used in DevOps demos)

## Project Structure

```
simple-webapp/
├── app.py              — Flask application
├── requirements.txt    — Python dependencies
├── Dockerfile          — Container definition
├── .gitignore
└── README.md
```

## Installation

### Prerequisites

- Python 3.x
- MySQL Server
- pip (Python package manager)

### Setup

Install system dependencies:

```bash
apt-get install -y python3 python3-setuptools python3-dev build-essential python3-pip default-libmysqlclient-dev
```

Install Python dependencies:

```bash
pip3 install -r requirements.txt
```

Create and activate virtual environment (recommended):

```bash
python3 -m venv venv
source venv/bin/activate
```

### Configuration

Update database credentials in `app.py`:
- Database host
- Database name
- Database user
- Database password

## Usage

Start the Flask application:

```bash
FLASK_APP=app.py flask run --host=0.0.0.0
```

Access the application:

```
http://localhost:5000
```

## API Endpoints

- `GET /` — Welcome page
- `GET /how%20are%20you` — Example endpoint returning "I am good, how about you?"

## Docker Deployment

Build the Docker image:

```bash
docker build -t simple-webapp:1.0 .
```

Run the container:

```bash
docker run -d \
  -e DB_HOST=<database-host> \
  -e DB_USER=<database-user> \
  -e DB_PASSWORD=<database-password> \
  -e DB_NAME=<database-name> \
  -p 5000:5000 \
  simple-webapp:1.0
```

## Skills Demonstrated

- Python programming
- Flask web framework
- MySQL database integration
- Containerization concepts
- Multi-tier application architecture
- DevOps fundamentals

## Use Cases

- **DevOps Training** — Demonstrates containerization and deployment concepts
- **Ansible Playbooks** — Used in infrastructure automation demonstrations
- **Docker Learning** — Example application for Docker training
- **CI/CD Pipelines** — Reference application for pipeline demonstrations

## Author

Ahmed Radi El-Refaei

GitHub: [@eng-ahmedradi](https://github.com/eng-ahmedradi)

## Notes

This application is intended for educational and demonstration purposes. Do not use database credentials in source code for production deployments. Use environment variables and secure secret management instead.
