# 🕉️ Pujapeeth Backend Service (`pujapeethsvc`)

This is the backend microservice for **Pujapeeth**, a modern puja booking platform.  
It provides REST APIs for managing puja appointments, priests, users, and notifications (email, SMS, WhatsApp).

---

## 🧱 Tech Stack

- **Language:** Go (>=1.22)
- **Framework:** [go-chi](https://github.com/go-chi/chi)
- **Database:** PostgreSQL
- **Containerization:** Docker & Docker Compose
- **Notifications:** Email / SMS / WhatsApp integrations (configurable)
- **Environment Configuration:** `.env`

---

## 📁 Project Structure

```bash
pujapeethsvc/
├── cmd/
│   └── server/
│       └── main.go                # Entry point of the service
│
├── internal/
│   ├── config/
│   │   └── config.go              # Environment variable loading
│   ├── db/
│   │   └── db.go                  # PostgreSQL connection setup
│   ├── handlers/
│   │   └── booking.go             # Booking-related HTTP handlers
│   ├── models/
│   │   └── booking.go             # Booking model definition
│   └── notifications/
│       └── notifier.go            # Notification sending logic (email/whatsapp)
│
├── migrations/
│   └── 0001_create_bookings.sql   # Initial database migration
│
├── Dockerfile                     # Docker build configuration
├── docker-compose.yml              # Local environment setup
└── .env.example                   # Example environment variables
```
---

## ⚙️ Setup Instructions

### 1️⃣ Clone the repository
```bash
git clone https://github.com/pujapeeth/pujapeethsvc.git
cd pujapeethsvc
```
---

### 2️⃣ Environment configuration
Copy .env.example to .env and update values:
```bash
cp .env.example .env
```

Example .env:
```bash
PORT=8080
DB_HOST=localhost
DB_PORT=5432
DB_USER=postgres
DB_PASSWORD=yourpassword
DB_NAME=pujapeeth
EMAIL_API_KEY=your_sendgrid_key
WHATSAPP_API_KEY=your_twilio_key
```

### 3️⃣ Run with Docker Compose
```bash
docker-compose up --build
```
This will:
- Start PostgreSQL
- Run the Go backend service
- Apply migrations automatically (if configured)


### 4️⃣ Run locally without Docker
Ensure PostgreSQL is running, then:
```bash
go mod tidy
go run ./cmd/server
```


### 🧘 Author

Pujapeeth Team
🙏 “Connecting Devotees with Priests the Modern Way”