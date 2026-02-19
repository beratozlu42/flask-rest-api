# Flask REST API

A modern, lightweight RESTful API built with **Flask**, **Flask-RESTful**, and **SQLAlchemy**. This project provides a robust foundation for managing user data with a SQLite backend.

## 🚀 Features

- **Full CRUD Support**: Create, Read, Update, and Delete user records.
- **Request Validation**: Built-in validation using `reqparse` to ensure data integrity.
- **Data Serialization**: Clean response formatting with `marshal_with`.
- **Database Integration**: Persistent storage using SQLite and SQLAlchemy ORM.

## 🛠️ Tech Stack

- **Framework**: [Flask](https://flask.palletsprojects.com/)
- **API Extension**: [Flask-RESTful](https://flask-restful.readthedocs.io/)
- **ORM**: [SQLAlchemy](https://www.sqlalchemy.org/)
- **Database**: SQLite

---

## 📦 Installation & Setup

### 1. Clone the Repository
```bash
git clone <repository-url>
cd flask-api
```

### 2. Set Up Virtual Environment
```bash
python3 -m venv .venv
source .venv/bin/activate  # On Windows: .venv\Scripts\activate
```

### 3. Install Dependencies
```bash
pip install -r requirements.txt
```
> **Note**: Ensure `flask-restful` and `flask-sqlalchemy` are installed.

### 4. Initialize the Database
Run the helper script to create the SQLite database and tables:
```bash
python3 create_db.py
```

### 5. Run the Application
```bash
python3 api.py
```
The server will start at `http://127.0.0.1:5000/`.

---

## 🛣️ API Endpoints

### Users Collection
| Method | Endpoint | Description |
| :--- | :--- | :--- |
| **GET** | `/api/users` | Retrieve all users |
| **POST** | `/api/users` | Create a new user |

### Individual User
| Method | Endpoint | Description |
| :--- | :--- | :--- |
| **GET** | `/api/users/<id>` | Get details of a specific user |
| **PATCH** | `/api/users/<id>` | Update user information |
| **DELETE** | `/api/users/<id>` | Remove a user |

---

## 📝 Usage Examples

### Create a User
```bash
curl -X POST http://127.0.0.1:5000/api/users \
     -H "Content-Type: application/json" \
     -d '{"name": "John Doe", "email": "john@example.com"}'
```

### Update a User
```bash
curl -X PATCH http://127.0.0.1:5000/api/users/1 \
     -H "Content-Type: application/json" \
     -d '{"name": "John Updated", "email": "john_new@example.com"}'
```

### Delete a User
```bash
curl -X DELETE http://127.0.0.1:5000/api/users/1
```

---

## 📂 Project Structure

- `api.py`: Main application file containing routes and models.
- `create_db.py`: Script to initialize the database schema.
- `database.db`: SQLite database file (generated after setup).
- `requirements.txt`: List of Python dependencies.
