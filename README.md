# Uber Clone — Full Stack Ride Booking Application

This project is a full-stack ride booking web application inspired by Uber.  
It allows users to register as riders or drivers, request rides, and interact through a real-time system powered by WebSockets.

---

## Overview

The application simulates the core workflow of a ride-hailing platform, including authentication, ride creation, and real-time communication between users.

It consists of:
- A backend API built with Node.js and Express
- A frontend application built with React (Vite)
- A MongoDB database for persistence
- A Socket.IO-based real-time communication layer

---

## Features

### Authentication and Authorization
- User registration and login
- Password hashing using bcrypt
- JWT-based authentication
- Role-based access (rider and driver)

### Ride Management
- Create ride requests with pickup and drop locations
- Store coordinates for mapping
- Ride lifecycle management:
  - requested → accepted → onway → completed
- Fetch all rides (for drivers or system view)

### Real-Time Communication
- Ride requests broadcast to connected clients using Socket.IO
- Instant updates between users

### Map Integration
- Interactive maps using Leaflet and React Leaflet
- Location input and visualization
- Coordinate-based ride handling

### Frontend Interface
- Built with React and Vite
- Material UI components
- Modular component structure
- Pages include:
  - Home (booking interface)
  - Login and Register
  - Rider Dashboard
  - Driver Dashboard

---

## Tech Stack

### Frontend
- React (Vite)
- Material UI
- React Router
- Axios
- Leaflet / React Leaflet
- Socket.IO Client

### Backend
- Node.js
- Express
- MongoDB (Mongoose)
- JWT (Authentication)
- bcrypt (Password hashing)
- Socket.IO

---

## Project Structure

project-root/
│
├── backend/
│   ├── models/
│   ├── routes/
│   ├── config/
│   └── index.js
│
├── frontend/
│   ├── components/
│   ├── pages/
│   ├── services/
│   └── main.jsx
│
└── README.md

---

## API Endpoints

### Authentication
- POST /api/auth/register
- POST /api/auth/login

### Rides
- POST /api/rides — Create a new ride
- GET /api/rides — Retrieve rides

---

## Authentication

Protected routes require a JWT token:

Authorization: Bearer <token>

---

## Real-Time Events

### Server → Client
- new-ride — Emitted when a new ride is created

### Client → Server
- Ride requests via Socket.IO connection

---

## Getting Started

### 1. Clone the Repository

git clone https://github.com/your-username/your-repo.git  
cd your-repo  

---

### 2. Backend Setup

cd backend  
npm install  

Create a .env file:

MONGO_URI=your_mongodb_uri  
JWT_SECRET=your_secret_key  
PORT=5000  

Run the backend server:

npm run dev  

---

### 3. Frontend Setup

cd frontend  
npm install  
npm run dev  

---

## Deployment Status

This project is currently running in a local development environment and has not yet been deployed to a live production URL.

Deployment can be completed using:
- Frontend: Vercel
- Backend: Render or Railway

Note:
WebSocket-based features (Socket.IO) require a backend platform that supports persistent connections.

---

## Limitations

- Ride matching is broadcast-based (not optimized)
- No dynamic pricing system
- No driver allocation logic
- Real-time system is basic and can be extended

---

## Future Improvements

- Implement intelligent driver matching
- Add dynamic pricing logic
- Improve real-time tracking of rides
- Add driver availability and analytics
- Enhance backend structure (controllers and services)

---

## License

This project is for educational purposes.
