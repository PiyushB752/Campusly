# Campusly

**Smart Campus & Student Productivity Platform**

Campusly is a full-stack web application designed to bring common student and campus activities into one centralized platform. It helps students manage academic information, assignments, tasks, attendance, campus events, and announcements through a unified interface.

The project focuses on building a practical, data-driven application with a separate frontend and backend, REST APIs, authentication, database integration, and reusable components.

## Features

* **Student Dashboard** — Centralized view of important academic and campus information.
* **Attendance Management** — Track attendance records and monitor academic attendance.
* **Assignments** — Create, view, organize, and manage assignments.
* **Tasks** — Manage personal and academic tasks.
* **Campus Events** — View and manage upcoming campus events.
* **Announcements** — Access important campus and academic announcements.
* **Authentication** — Secure user registration, login, and protected application routes.
* **Profile Management** — Manage user profile information.
* **Responsive Interface** — Designed for desktop, tablet, and mobile screens.
* **AI Assistance** — Server-side AI integration for student productivity features.

## Tech Stack

### Frontend

* React.js
* JavaScript
* Vite
* HTML5
* CSS3

### Backend

* Node.js
* Express.js
* REST APIs
* JWT Authentication

### Database

* MongoDB
* Mongoose

### AI & Services

* Groq API
* Environment-based API configuration

### Development Tools

* Git
* GitHub
* npm
* VS Code

## Architecture

Campusly follows a separated frontend/backend architecture.

```text
Campusly
│
├── client/
│   ├── components/
│   ├── pages/
│   ├── services/
│   ├── hooks/
│   ├── styles/
│   └── ...
│
└── server/
    ├── routes/
    ├── controllers/
    ├── models/
    ├── middleware/
    ├── services/
    └── server.js
```

The React frontend communicates with the Express backend through REST APIs. The backend handles authentication, business logic, database operations, and external API integrations.

```text
React Client
     │
     │ REST API
     ▼
Express / Node.js
     │
     ├──────────────► MongoDB
     │
     └──────────────► AI Services
```

## Authentication

Campusly uses JWT-based authentication to protect user-specific resources.

The authentication flow is:

```text
User
  │
  ▼
Login / Register
  │
  ▼
Express API
  │
  ▼
Validate Credentials
  │
  ▼
Generate JWT
  │
  ▼
Authenticated Requests
```

Protected API routes verify the user's authentication token before allowing access to protected resources.

## Data Management

Campusly manages multiple types of application data, including:

* Users
* Attendance records
* Assignments
* Tasks
* Events
* Announcements

MongoDB is used as the primary database, with Mongoose providing schema definitions and database interaction from the Node.js backend.

## API Structure

The backend exposes RESTful API endpoints for different application resources.

Example endpoint groups include:

```text
/api/auth
/api/users
/api/attendance
/api/assignments
/api/tasks
/api/events
/api/announcements
```

The exact endpoints and request/response structures can be found in the backend source code.

## Environment Variables

Create a `.env` file in the server directory.

Example:

```env
PORT=5000
MONGODB_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
GROQ_API_KEY=your_groq_api_key
```

Never commit real credentials or API keys to the repository.

## Getting Started

### Prerequisites

Make sure you have the following installed:

* Node.js
* npm
* MongoDB or a MongoDB Atlas database
* Git

### Clone the Repository

```bash
git clone https://github.com/PiyushB752/Campusly.git
cd Campusly
```

### Install Dependencies

Install the frontend dependencies:

```bash
cd client
npm install
```

Install the backend dependencies:

```bash
cd ../server
npm install
```

### Configure Environment Variables

Create the required `.env` file inside the `server` directory and add your database connection string, JWT secret, and AI API key.

### Start the Backend

```bash
cd server
npm run dev
```

The backend runs on:

```text
http://localhost:5000
```

### Start the Frontend

Open another terminal:

```bash
cd client
npm run dev
```

The frontend will be available at the Vite development URL shown in the terminal.

## Development

The project is structured to keep frontend presentation and backend responsibilities separate.

### Frontend

Responsible for:

* User interface
* Client-side routing
* API communication
* Application state
* User interactions
* Responsive layouts

### Backend

Responsible for:

* REST API endpoints
* Authentication
* Business logic
* Database operations
* Request validation
* External service integrations

This separation makes the application easier to maintain and extend.

## Error Handling

The application includes handling for common application states such as:

* Loading states
* Empty states
* API errors
* Authentication failures
* Invalid requests
* Database errors

The frontend provides appropriate feedback when backend operations fail instead of assuming every request succeeds.

## Security Considerations

Campusly follows several basic application security practices:

* JWT-based authentication
* Protected API routes
* Environment variables for secrets
* Server-side handling of sensitive API keys
* Input validation
* Separation of frontend and backend responsibilities

Sensitive credentials should never be stored directly in frontend source code or committed to GitHub.

## Project Goals

The main goals of Campusly are to:

1. Provide students with a centralized productivity platform.
2. Practice full-stack application development.
3. Build and consume RESTful APIs.
4. Work with database-backed application data.
5. Implement authentication and protected resources.
6. Build a maintainable frontend/backend architecture.
7. Integrate AI functionality into a practical application.

## Future Improvements

Potential improvements include:

* Role-based access control for students, faculty, and administrators
* Advanced attendance analytics
* Calendar integration
* Notification system
* Improved search and filtering
* More comprehensive API documentation
* Automated testing
* Production monitoring and logging

## License

This project is intended for educational and portfolio purposes.

## Deployment

link - https://campusly-peach.vercel.app/