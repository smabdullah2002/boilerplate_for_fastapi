# FastAPI Boilerplate

A structured **FastAPI boilerplate** for building scalable APIs with clean architecture.  
This template separates concerns into **features** (users, products, etc.), while keeping shared modules (database, configs, base classes) centralized.
---

## 📂 Project Structure

app/
├── apis/
│ └── base.py # Collects and includes all routers
├── core/
│ └── config.py # App configuration (env vars, settings)
├── feature_1/ # Example feature (rename to your own)
│ ├── models.py
│ ├── routes.py
│ ├── schemas.py
│ └── services.py
├── feature_2/ # Another feature (rename to your own)
│ ├── models.py
│ ├── routes.py
│ ├── schemas.py
│ └── services.py
├── shared/
│ ├── base_class.py # SQLAlchemy Base
│ └── ... # Common utils (deps, exceptions, etc.)
├── database.py # DB engine & session
├── base.py # Imports all models to register with Base
├── main.py # FastAPI entrypoint
.env # Environment variables
requirements.txt # Dependencies

---

## ⚙️ Setup

1️⃣ Clone the repo
```bash
git clone https://github.com/yourusername/fastapi-boilerplate.git
cd fastapi-boilerplate

2️⃣ Create & activate virtual environment
python -m venv venv
source venv/bin/activate   # Linux / Mac
venv\Scripts\activate      # Windows

3️⃣ Install dependencies
pip install -r requirements.txt

Files:
main.py → entry point where you create the FastAPI app and include routers.
config.py → keeps environment variables/settings (like SECRET_KEY, DB URL).
database.py → database connection
base.py → This file collects all models so Alembic / SQLAlchemy can see them.
app/shared/base_class.py → defines the reusable Base class.
features/services → functionility of a specific feature (eg. create_blog, update_blog etc)

