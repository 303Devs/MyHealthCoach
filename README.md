# MyHealthCoach

A full-stack health and fitness tracking application built by [303Devs](https://github.com/303Devs). MyHealthCoach enables users to log workouts, track caloric intake and macros, visualize progress with charts, and review their fitness history through a calendar interface.

Built on the PERN stack — PostgreSQL, Express, React (Next.js), and Node.js — with Docker support and a CI pipeline.

---

## Tech Stack

![Next.js](https://img.shields.io/badge/Next.js-black?style=flat-square&logo=next.js)
![React](https://img.shields.io/badge/React-61DAFB?style=flat-square&logo=react&logoColor=black)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat-square&logo=typescript&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-339933?style=flat-square&logo=node.js&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white)

### Frontend (`Front-end/`)

| Category | Technology |
|---|---|
| Framework | Next.js + React |
| Language | TypeScript |
| Styling | Tailwind CSS |
| Charts | react-chartjs-2 |
| Calendar | react-calendar |
| HTTP Client | axios |
| Auth (client) | bcryptjs, jwt-decode |
| Utilities | react-icons, react-confetti, react-modal, react-select, react-use, uuid |

### Backend (`Back-end/`)

| Category | Technology |
|---|---|
| Runtime | Node.js |
| Framework | Express |
| Database | PostgreSQL (via `pg`) |
| Auth | JWT middleware |
| HTTP Client | axios |
| Utilities | cors, dotenv, bluebird |
| Testing | Jest |
| Containerization | Docker + docker-compose |
| CI | GitHub Actions |

---

## Features

- **Workout Logging** — Record exercises, sets, reps, and duration
- **Calorie and Macro Tracking** — Log meals and nutritional data
- **Data Visualization** — Interactive charts showing progress over time (Chart.js via react-chartjs-2)
- **Calendar View** — Browse and review workout history by date
- **User Authentication** — JWT-based auth with bcrypt password hashing
- **REST API** — Organized Express backend with controllers, routes, middleware, and models
- **Database Schemas** — Managed PostgreSQL schemas with structured migrations
- **Docker Support** — `Dockerfile` and `docker-compose.yml` for both development and CI environments
- **Automated Testing** — Jest test suite with GitHub Actions integration
- **Continuous Integration** — CI pipeline via GitHub Actions (`.github/workflows`)

---

## Project Structure

```
myhealthcoach/
├── Front-end/                     # Next.js frontend
│   ├── pages/                     # Next.js page routes
│   ├── components/                # Reusable UI components
│   ├── context/                   # React context providers
│   ├── styles/                    # Global and component styles
│   ├── public/                    # Static assets
│   ├── __tests__/                 # Frontend tests
│   ├── example.env                # Environment variable template
│   ├── Dockerfile
│   └── package.json
└── Back-end/                      # Express + PostgreSQL API
    ├── app.js                     # Express app entry
    ├── appListen.js               # Server startup
    ├── config.js                  # Configuration
    ├── controllers/               # Route handlers
    ├── routes/                    # Express router definitions
    ├── middleware/                 # Auth and other middleware
    ├── model/                     # Data models
    ├── db/                        # Database connection
    ├── schemas/                   # PostgreSQL schema definitions
    ├── __tests__/                 # Backend tests
    ├── __mocks__/                 # Test mocks
    ├── docker-compose.yml
    ├── docker-compose-ci.yml
    ├── Dockerfile
    └── package.json
```

---

## Getting Started

### Prerequisites

- Node.js 18+
- PostgreSQL (local instance or cloud provider)
- Docker and Docker Compose (optional, for containerized setup)

### Backend Setup

```bash
git clone https://github.com/303Devs/MyHealthCoach.git
cd MyHealthCoach/Back-end
npm install
```

Copy `example.env` (if present) or create a `.env` file with your database credentials:

```bash
DATABASE_URL=postgresql://user:password@localhost:5432/myhealthcoach
JWT_SECRET=your_jwt_secret
PORT=5000
```

Apply the database schemas from the `schemas/` directory, then start the server:

```bash
npm start
```

### Frontend Setup

```bash
cd ../Front-end
npm install
```

Create a `.env.local` file pointing to your backend:

```bash
NEXT_PUBLIC_API_URL=http://localhost:5000
```

```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000).

### Docker Setup

```bash
cd Back-end
docker-compose up
```

This starts the Express API and a PostgreSQL instance together.

### Running Tests

```bash
# Backend
cd Back-end && npm test

# Frontend
cd Front-end && npm test
```

---

## Screenshots

<!-- Add screenshots here -->

---

## CI / CD

GitHub Actions workflows are located in `Back-end/.github/` and run the Jest test suite on each push. The `docker-compose-ci.yml` file is used within the CI environment to spin up a PostgreSQL service for integration tests.

---

## Status

Portfolio project — actively developed by 303Devs. Not currently deployed to a public production URL.

---

Built by [303Devs](https://github.com/303Devs)
