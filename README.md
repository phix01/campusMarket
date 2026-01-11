# Campus Market — University Marketplace (Flutter + Flask)

**Short description:** This repository is a monorepo containing a Flutter mobile client (`frontend/`) and a Flask REST API (`backend/`). The project demonstrates a simple marketplace for campus users (listings, messaging, appointments, conversations).

```
campus_market/
├─ backend/          # Flask + SQLAlchemy API
├─ frontend/         # Flutter client
├─ INTEGRATION_STATUS.md
└─ README.md
```

---

## 🚀 Quick Start

### Backend (Flask)
1. Make sure you have Python 3.8+ installed.
2. Create and activate a virtual environment, install dependencies:

```bash
cd backend
python -m venv venv
source venv/bin/activate   # Linux / macOS
pip install -r requirements.txt
```

3. Run the server:

```bash
python app.py
# or from repo root
python backend/app.py
```

> Note: By default the app uses SQLite (`sqlite:///campus.db`) and will create the DB automatically on first run (`db.create_all()`).

### Frontend (Flutter)
1. Install Flutter SDK (https://flutter.dev).
2. Run the app:

```bash
cd frontend
flutter pub get
flutter run
```

> Tip: When using an Android emulator, point the client to the backend using an appropriate base URL (e.g. `http://10.0.2.2:5000/api`).

---

## ⚙️ Configuration & Environment Variables

Backend configuration is in `backend/config.py`. Important settings include:

- `SECRET_KEY` (default: `dev_secret_key`)
- `JWT_SECRET_KEY` (default: `jwt_dev_secret`)
- `SQLALCHEMY_DATABASE_URI` (default: `sqlite:///campus.db`)
- `UPLOAD_FOLDER` (default: `backend/uploads`) — created on startup

Example (bash):

```bash
export SECRET_KEY="your_secret_key"
export JWT_SECRET_KEY="your_jwt_secret"
```

If you want to use a different database, update `SQLALCHEMY_DATABASE_URI` in `backend/config.py`.

---

## 📍 Main API Endpoints

- `POST /api/auth/...` — Authentication (register / login)
- `GET/POST /api/listings/...` — Listings (create, list, update, delete)
- `GET/POST /api/messages/...` — Messages
- `GET/POST /api/appointments/...` — Appointments
- `GET/POST /api/conversations/...` — Conversations

Static / uploaded files are served via:

```
GET /uploads/<filename>
```

---

## ✅ Tests

- Frontend: `flutter test`
- Backend: No automated tests included yet — I can add `pytest` tests if desired.

---

## 🤝 Contributing

1. Fork the repo
2. Create a branch (`feature/your-feature`)
3. Commit your changes with clear messages
4. Open a pull request and describe your changes

For large features, please open an issue first to discuss the design.

---


