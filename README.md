🚚 Last-Mile Delivery Tracker

A full-stack **Last-Mile Delivery Tracking System** built using the **MERN Stack** (MongoDB, Express.js, React, Node.js) and containerized with **Docker Compose**. The application provides role-based access for **Admins**, **Delivery Agents**, and **Customers** to efficiently manage and track delivery operations.

---

## 📌 Features

### 👤 Customer

* Register and log in securely
* Create new delivery orders
* View order history
* Track order details and delivery status

### 🚴 Delivery Agent

* View assigned delivery orders
* Update order delivery status

### 🛠️ Admin

* Dashboard overview
* Manage delivery agents
* Manage customer orders
* Manage delivery zones
* Manage rate cards
* Automatic order assignment

---

## 🏗️ Tech Stack

### Frontend

* React.js
* Vite
* React Router
* Tailwind CSS
* Axios

### Backend

* Node.js
* Express.js
* MongoDB
* Mongoose
* JWT Authentication

### DevOps

* Docker
* Docker Compose

---

## 📂 Project Structure

```text
Last-Mile-Delivery-Tracker/
├── client/
│   ├── src/
│   ├── Dockerfile
│   └── package.json
│
├── server/
│   ├── config/
│   ├── controllers/
│   ├── middleware/
│   ├── models/
│   ├── routes/
│   ├── services/
│   ├── utils/
│   ├── tests/
│   ├── Dockerfile
│   └── package.json
│
├── compose.yml
└── README.md
```

---

# ⚙️ Prerequisites

Install the following before running the project:

* Docker
* Docker Compose (or Docker Desktop)

Verify installation:

```bash
docker --version
docker compose version
```

---

# 🔐 Environment Variables

## Server (`server/.env`)

```env
PORT=5000

MONGO_URI=mongodb://mongo:27017/lastmile

JWT_SECRET=your_secret_key
```

## Client (`client/.env`)

```env
VITE_API_URL=http://localhost:5000/api
```

---

# 🚀 Running the Project

Clone the repository:

```bash
git clone <repository-url>
cd Last-Mile-Delivery-Tracker
```

Build and start all services:

```bash
docker compose up --build
```

Run in detached mode:

```bash
docker compose up -d --build
```

---

# 📦 Docker Services

| Service | Port  | Description      |
| ------- | ----- | ---------------- |
| MongoDB | 27017 | Database         |
| Server  | 5000  | Express REST API |
| Client  | 5173  | React Frontend   |

---

# 🌐 Application URLs

| Service     | URL                       |
| ----------- | ------------------------- |
| Frontend    | http://localhost:5173     |
| Backend API | http://localhost:5000     |
| MongoDB     | mongodb://localhost:27017 |

---

# 📋 Verify Running Containers

```bash
docker ps
```

Expected output:

```
client
server
mongo
```

---

# 🛠️ Useful Docker Commands

### Build and Start

```bash
docker compose up --build
```

### Run in Background

```bash
docker compose up -d
```

### View Logs

```bash
docker compose logs
```

### View Logs for Backend

```bash
docker compose logs -f server
```

### View Logs for Frontend

```bash
docker compose logs -f client
```

### Stop Containers

```bash
docker compose down
```

### Remove Containers and Volumes

```bash
docker compose down -v
```

### Restart Services

```bash
docker compose restart
```

---

# 🌱 Seed Sample Data

Run the seed script inside the backend container:

```bash
docker exec -it server node utils/seed.js
```
```
Default Seed Accounts
The database seed command generates the following default credentials for testing all roles:

Role	Username / Email	Password	Details
Admin	admin@lastmile.com	Password123	Direct access to zones, rate cards, and agent manual overrides.

Customer	customer@lastmile.com	Password123	Direct access to book orders and reschedule failed deliveries.

Agent 1	agent1@lastmile.com	Password123	North Zone delivery agent.

Agent 2	agent2@lastmile.com	Password123	West Zone delivery agent.

Agent 3	agent3@lastmile.com	Password123	South Zone delivery agent.

```


---

# 📡 REST API Endpoints

## Authentication

| Method | Endpoint             |
| ------ | -------------------- |
| POST   | `/api/auth/register` |
| POST   | `/api/auth/login`    |

## Orders

| Method | Endpoint          |
| ------ | ----------------- |
| POST   | `/api/orders`     |
| GET    | `/api/orders`     |
| GET    | `/api/orders/:id` |

## Admin

* Manage Agents
* Manage Orders
* Manage Delivery Zones
* Manage Rate Cards

---

# 🧪 Running Tests

Backend integration tests:

```bash
docker exec -it server npm test
```

---

# 🐞 Troubleshooting

### MongoDB Connection Failed

Verify your backend `.env` contains:

```env
MONGO_URI=mongodb://mongo:27017/lastmile
```

---

### Backend Not Starting

Check server logs:

```bash
docker compose logs server
```

---

### Frontend Cannot Reach Backend

Ensure:

* Backend container is running
* `VITE_API_URL=http://localhost:5000`
* Port **5000** is available

---

### Port Already in Use

Stop conflicting services or modify the exposed ports in `compose.yml`.

---

# 📸 Screenshots

You can add screenshots here.

```
docs/
├── login.png
├── dashboard.png
├── orders.png
└── admin.png
```

Example:

```markdown
## Login

![Login](docs/login.png)
```

---

# 🔮 Future Enhancements

* Live GPS tracking
* Real-time notifications
* Email/SMS updates
* Payment integration
* Analytics dashboard
* Delivery route optimization
* Admin reports
* Mobile application

---

# 👨‍💻 Author

Developed as a MERN Stack + Docker practice project demonstrating a complete Last-Mile Delivery Tracking System.

---

# 📄 License

This project is intended for educational and learning purposes.
