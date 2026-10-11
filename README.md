# EMedica

EMedica is a healthcare management system with a React dashboard frontend and a Node.js/Express backend. It provides role-based interfaces for patients, doctors, administrators, supervisors, trainees, and super administrators.

## Features

- Role-based healthcare dashboards
- Patient, doctor, staff, and user management
- Appointment scheduling and administration
- Medical records and prescriptions
- Consultations and assigned-patient workflows
- Hospital resources, analytics, and map views
- JWT-based authentication endpoints
- MySQL database schema for healthcare data

## Project structure

```text
Emedica/
├── Frontend/
│   └── project/       # React + Vite + TypeScript application
└── backend/           # Node.js + Express API and MySQL schema
```

## Requirements

- Node.js 18 or newer
- npm
- MySQL 8 or compatible

## Frontend setup

```bash
cd Frontend/project
npm install
npm run dev
```

The frontend runs at [http://localhost:5173](http://localhost:5173).

To create a production build:

```bash
npm run build
```

## Backend setup

Create or update `backend/.env` with your local MySQL configuration:

```env
PORT=5000
JWT_SECRET=replace_with_a_secure_secret
DB_HOST=localhost
DB_USER=root
DB_PASSWORD=your_mysql_password
DB_NAME=emedica
```

Install dependencies and start the API:

```bash
cd backend
npm install
npm run dev
```

The backend runs at [http://localhost:5000](http://localhost:5000).

## Database setup

Create the database and tables using the project schema:

```bash
mysql -u root -p < backend/config/schema.sql
```

The schema creates the `emedica` database and the core tables for users, patients, doctors, appointments, medical records, prescriptions, consultations, and roles.

Verify the tables:

```bash
mysql -u root -p -e "USE emedica; SHOW TABLES;"
```

Never commit `backend/.env` or any other file containing passwords, tokens, or production credentials.

## API routes

The backend currently exposes authentication routes under:

```text
/api/auth
```

Additional healthcare routes and data models are included in the project structure for continued development.

## Available scripts

### Frontend

| Command | Description |
| --- | --- |
| `npm run dev` | Start the Vite development server |
| `npm run build` | Create a production build |
| `npm run lint` | Run ESLint |
| `npm run preview` | Preview the production build |

### Backend

| Command | Description |
| --- | --- |
| `npm run dev` | Start the backend with automatic reload |
| `npm start` | Start the backend with Node.js |

## Security notes

- Use a strong, unique `JWT_SECRET` outside local development.
- Store database credentials only in local environment files or a secure secret manager.
- Configure HTTPS, access controls, and production database permissions before deployment.

## License

No license has been specified for this project yet.
