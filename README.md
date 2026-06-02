# 🎨 Collaborative Whiteboard App

A real-time collaborative whiteboard built using the **MERN Stack** and **Socket.IO**, allowing multiple users to draw together and share cursor movements instantly — no authentication required. Simply share a room code and start collaborating!

---

## 🚀 Project Overview

This project is a real-time collaborative whiteboard web application where multiple users can join a shared room and draw together simultaneously.

Users can join rooms using simple alphanumeric codes, and all drawing actions and cursor movements are synchronized instantly across connected clients.

---

## 🛠️ Tech Stack

| Layer                   | Technology           |
| ----------------------- | -------------------- |
| Frontend                | React.js             |
| Backend                 | Node.js + Express.js |
| Database                | MongoDB              |
| Real-Time Communication | Socket.IO            |
| Styling                 | Tailwind CSS / CSS   |

---

## ✨ Features

### 🏠 Room Management

* Join a room using a 6–8 character alphanumeric code.
* No login or registration required.
* Rooms are created automatically if they do not exist.

### ✏️ Drawing Features

* Pencil drawing tool.
* Multiple color options (Black, Red, Blue, Green).
* Adjustable stroke width using a slider.
* Clear canvas functionality.
* Smooth drawing experience using the HTML5 Canvas API.

### ⚡ Real-Time Collaboration

* Live drawing synchronization across all connected users.
* Real-time cursor tracking with unique colors for each user.
* Active user count display for each room.
* Multi-tab synchronization support.

---

## 📂 Project Structure

```text
project-root/
├── client/
│   ├── src/
│   │   ├── components/
│   │   │   ├── RoomJoin.jsx
│   │   │   ├── Whiteboard.jsx
│   │   │   ├── DrawingCanvas.jsx
│   │   │   ├── Toolbar.jsx
│   │   │   └── UserCursors.jsx
│   │   ├── socket.js
│   │   └── App.js
│   └── package.json
│
├── server/
│   ├── models/
│   │   └── Room.js
│   ├── routes/
│   │   └── roomRoutes.js
│   ├── socket/
│   │   └── socketHandlers.js
│   ├── server.js
│   └── package.json
│
└── README.md
```

---

## ⚙️ Installation & Setup

### Prerequisites

Make sure you have the following installed:

* Node.js (v16 or higher)
* MongoDB (Local or Atlas)
* npm or yarn

---

### 1️⃣ Clone the Repository

```bash
git clone https://github.com/your-username/collab-whiteboard.git
cd collab-whiteboard
```

---

### 2️⃣ Backend Setup

```bash
cd server
npm install
```

Create a `.env` file inside the `server/` directory:

```env
PORT=8000
MONGODB_URI=your_mongodb_connection_string
```

Start the backend server:

```bash
npm start
```

---

### 3️⃣ Frontend Setup

```bash
cd ../client
npm install
```

Create a `.env` file inside the `client/` directory:

```env
VITE_BACKEND_URL=http://localhost:8000
```

Start the frontend:

```bash
npm run dev
```

---

## 📚 API Documentation

### Join or Create Room

| Method | Endpoint          |
| ------ | ----------------- |
| POST   | `/api/rooms/join` |

#### Request Body

```json
{
  "roomId": "abc123"
}
```

---

### Get Room Details

| Method | Endpoint             |
| ------ | -------------------- |
| GET    | `/api/rooms/:roomId` |

---

## 🔌 Socket.IO Events

### Client → Server

| Event          | Description                |
| -------------- | -------------------------- |
| `join-room`    | Join a room                |
| `cursor-move`  | Send cursor position       |
| `draw-start`   | Start drawing              |
| `draw-move`    | Continue drawing           |
| `draw-end`     | Finish drawing             |
| `clear-canvas` | Clear canvas for all users |

### Server → Client

| Event           | Description                 |
| --------------- | --------------------------- |
| `user-count`    | Updated active user count   |
| `cursor-update` | Receive cursor positions    |
| `draw-start`    | Start drawing event         |
| `draw-move`     | Receive drawing data        |
| `draw-end`      | End drawing event           |
| `clear-canvas`  | Clear canvas across clients |

---

## 🏗️ Architecture Overview

```text
[Client Browser]
        │
        ▼
[React Frontend]
        │
        ▼
[Express + Socket.IO Server]
        │
        ▼
[MongoDB]
```

---

## 🚀 Deployment Guide

### Backend Deployment

Deploy the backend using:

* Render
* Railway
* Vercel
* VPS / Docker Hosting

Ensure:

* WebSocket transport is enabled.
* CORS is configured correctly.
* MongoDB Atlas connection string is added to environment variables.

Example production environment variables:

```env
PORT=8000
MONGODB_URI=mongodb+srv://username:password@cluster.mongodb.net/whiteboard
```

---

### Frontend Deployment

Deploy the frontend using:

* Vercel
* Netlify

Set the following environment variable:

```env
VITE_BACKEND_URL=https://your-backend-url.com
```

---

### MongoDB Atlas Setup

1. Create a MongoDB Atlas cluster.
2. Add your backend server IP to the whitelist.
3. Replace the local MongoDB URI with the Atlas URI.
4. Redeploy the backend.

---

## ✅ Current Status

* [x] Join/Create room via room code
* [x] Real-time drawing synchronization
* [x] Real-time cursor tracking
* [x] Multi-tab synchronization
* [x] Shared canvas clearing
* [x] Active user tracking

---

## 📄 License

made with ❤️ by Vishal

