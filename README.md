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
