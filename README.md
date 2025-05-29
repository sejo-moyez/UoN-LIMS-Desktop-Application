# Calibration & Preventive-Maintenance Manager (FME-562)

A cross-platform desktop application that **automates calibration and preventive-maintenance schedules** for laboratory and workshop equipment.  
Built for the University of Nairobi Faculty of Engineering, yet architected to plug into any small-to-medium lab environment.

---

## ✨  Key features
* **Central asset register** – searchable, drag-and-drop CSV import/export  
* **Automatic schedules** – APScheduler polls every 15 min and flags items due or overdue  
* **Real-time alerts** – desktop pop-ups *and* SMS via TextSMS Kenya  
* **Role-based access control** – Admin, Technician, User  
* **KPI dashboard** – live MTBF, MTTR, Availability, downtime/compliance charts  
* **Audit-proof reporting** – PDF & CSV exports, immutable task logs  
* **Modular stack** – ready for future web/mobile UI and IoT sensor feeds

---

## 🏗️  Tech stack
| Layer | Tech |
|-------|------|
| Front-end | **PySide 6** (Qt 6.6) |
| Back-end | **Python 3.11**, **PostgreSQL 15**, **psycopg2** |
| Scheduling | **APScheduler 3.10** |
| Messaging | **TextSMS Kenya REST API** |
| Auth / Security | bcrypt-hashed passwords, `.env` secrets |
| Packaging | `pyproject.toml` + **Poetry** |

---

## 🚀  Quick start

### 1.  Clone & set up a virtual env
```bash
git clone https://github.com/your-handle/calib-pm-manager.git
cd calib-pm-manager
python -m venv .venv
source .venv/bin/activate  # Windows: .venv\Scripts\activate
# UoN-LIMS-Desktop-Application



2. Install dependencies
bash
Copy
Edit
pip install -r requirements.txt
3. Configure secrets
Create a .env file in the project root:

ini
Copy
Edit
DB_HOST=localhost
DB_PORT=5432
DB_NAME=calibpm
DB_USER=postgres
DB_PASS=postgres
SMS_API_KEY=your_textsms_api_key
4. Initialise the database
bash
Copy
Edit
psql -U postgres -c "CREATE DATABASE calibpm;"
python tools/init_db.py
5. Load demo data (optional)
bash
Copy
Edit
python tools/load_demo_assets.py sample_data/equipment_demo.csv
6. Run the app
bash
Copy
Edit
python calibpm/main.py
Login credentials (demo):

sql
Copy
Edit
Admin      admin@example.com   admin123
Technician tech@example.com    tech123
User       user@example.com    user123
📝 Architecture
css
Copy
Edit
[ PySide 6 Client ]
        │ psycopg2
[ PostgreSQL ]───[ APScheduler Task ]
        │ REST
[ TextSMS Kenya Gateway ]
Full diagram & sequence charts are in /docs/architecture.

🧪 Tests
bash
Copy
Edit
pytest -q
Unit, integration, and 10-concurrent-client load tests (Locust) live in tests/.

📦 Packaging
poetry build – builds a wheel for PyPI

pyinstaller calibpm.spec – generates a one-folder executable for Windows/Linux/Mac

🤝 Contributing
Fork, branch from develop, follow Conventional Commits.

Run pre-commit install – black, isort, flake8 are enforced.

Submit a PR → GitHub Actions will lint & run tests.

🪪 License
MIT – free for academic, research, and commercial use.
