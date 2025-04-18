# Real-Time Chat Application

A modern real-time chat application built with a microservice architecture using React, TypeScript, Node.js, Express, Socket.IO, and MongoDB.

## Project Overview

This project is a full-featured chat application consisting of two main components:

- **chat-frontend**: Client-side application built with React and TypeScript
- **chat-backend**: Server-side application built with Node.js, Express, and Socket.IO

The application allows users to:
- Enter the chat by providing a username
- Send and receive messages in real-time
- View message history with infinite scrolling
- Track message status (sending, sent, error)

## Project Structure

The project is organized as a monorepo using Git submodules:

```
chat-project/
├── .gitmodules                # Git submodules configuration
├── docker-compose.yml         # Docker Compose configuration for running the entire project
├── README.md                  # This file
├── chat-backend/              # Backend submodule
│   ├── src/                   # Backend source code
│   │   ├── controllers/       # API controllers
│   │   ├── database/          # Database connection settings
│   │   ├── models/            # Mongoose models
│   │   ├── routes/            # API routes
│   │   ├── services/          # Business logic
│   │   ├── socket/            # Socket.IO handlers
│   │   ├── utils/             # Utilities
│   │   ├── validations/       # Data validation
│   │   └── index.ts           # Application entry point
│   └── ...                    # Other backend configuration files
└── chat-frontend/             # Frontend submodule
    ├── src/                   # Frontend source code
    │   ├── components/        # React components
    │   ├── context/           # React contexts
    │   ├── pages/             # Application pages
    │   ├── services/          # Services (API, Socket, etc.)
    │   └── ...                # Other frontend folders
    └── ...                    # Other frontend configuration files
```

## Technologies

### Backend
- Node.js
- Express
- Socket.IO
- MongoDB with Mongoose
- TypeScript
- Zod for validation

### Frontend
- React
- TypeScript
- Socket.IO Client
- TailwindCSS
- React Router
- Vite

### DevOps
- Docker
- Docker Compose

## Getting Started

### Prerequisites

- Docker and Docker Compose
- Node.js (v16 or higher)
- npm or yarn

### Installation

Clone the repository with all submodules:

```bash
git clone --recurse-submodules git@github.com:RomSribn/chat-project.git
cd chat-project
```

### Running with Docker

The easiest way to run the entire application is using Docker Compose:

```bash
# Start all services
docker-compose up --build

# Start in detached mode
docker-compose up --build -d

# Stop all services
docker-compose down
```

This will start:
- MongoDB database on port 27017
- Backend service on port 4000
- Frontend service on port 8080

### Running Locally for Development

#### Backend

```bash
cd chat-backend
npm install
npm run dev
```

The backend will be available at http://localhost:4000.

#### Frontend

```bash
cd chat-frontend
npm install
npm run dev
```

The frontend will be available at http://localhost:5173.

## Submodule Documentation

For more detailed information about each component, please refer to their respective README files:

- [Frontend Documentation](chat-frontend/README.md)
- [Backend Documentation](chat-backend/README.md)

## Environment Variables

### Backend

- `PORT`: Server port (default: 4000)
- `APP_MONGO_URI`: MongoDB connection string (default: mongodb://localhost:27017/chat-app)
- `NODE_ENV`: Environment (development, production)

### Frontend

- `VITE_API_BASE_URL`: Backend API URL (default: http://localhost:4000/api)
- `VITE_SOCKET_BASE_URL`: Socket.IO server URL (default: http://localhost:4000)
- `VITE_ERROR_TRACKING_ENABLED`: Enable error tracking (default: false)
- `VITE_ERROR_TRACKING_URL`: Error tracking endpoint (default: http://localhost:4000/errors)
