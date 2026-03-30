# TekUpStudents

A full-featured student management web application built with **Angular 16**, designed for TekUp university. The platform provides separate portals for students and administrators, supporting surveys, certification management, requests, and complaints.

---

## Features

- **Authentication** — JWT-based login with role-based access control (student / admin)
- **Student Panel** — Personal dashboard for students to manage their profile and activities
- **Admin Panel** — Administrative dashboard for managing students and platform data
- **Survey Module** — Create and submit surveys powered by SurveyJS
- **Reclamations / Complaints** — Submit and track complaints
- **Demands / Requests** — Submit and follow up on administrative requests
- **Certification Management** — Add and view certifications
- **Charts & Analytics** — Data visualizations via Chart.js
- **Responsive UI** — Built with Bootstrap 5, PrimeNG, and ng-bootstrap

---

## Tech Stack

| Layer | Technology |
|---|---|
| Framework | Angular 16 |
| UI Libraries | Bootstrap 5, PrimeNG 16, ng-bootstrap 15 |
| Forms | Angular Reactive Forms |
| Auth | JWT (`jwt-decode`, `json-web-token`) |
| Permissions | ngx-permissions |
| Surveys | SurveyJS (survey-angular-ui, survey-pdf) |
| Charts | Chart.js 4 |
| Styling | Font Awesome, PrimeFlex, PrimeIcons |

---

## Prerequisites

- [Node.js](https://nodejs.org/) v18+
- [Angular CLI](https://angular.io/cli) v16

---

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/maryem012/PROJECT2023.git
cd PROJECT2023
```

### 2. Install dependencies

```bash
npm install --legacy-peer-deps
```

### 3. Start the development server

```bash
npm start
```

Navigate to `http://localhost:4200/`. The application reloads automatically when source files change.

---

## Available Routes

| Path | Component | Access |
|---|---|---|
| `/login` | Login | Public |
| `/student` | Student Panel | Student |
| `/survey` | Survey | Student |
| `/reclamation` | Submit Complaint | Student |
| `/mycomp` | My Complaints | Student |
| `/req` | Submit Request | Student |
| `/myreq` | My Requests | Student |
| `/addNew` | Add Certification | Student |
| `/admin` | Admin Panel | Admin |

---

## Build

```bash
npm run build
```

Production build artifacts are output to the `dist/tek-up-students/` directory.

---

## Running Tests

```bash
npm test
```

Unit tests are executed via [Karma](https://karma-runner.github.io) and Jasmine.

---

## Docker

The application is containerized using a multi-stage Docker build (Node.js builder → Nginx server).

### Build the image

```bash
docker build -t tekupstudents .
```

### Run the container

```bash
docker run -p 8080:80 tekupstudents
```

The app will be available at `http://localhost:8080`.

---

## CI/CD Pipeline (Jenkins)

The project includes a Jenkins pipeline (`Jenkinsfile`) that automates the full delivery workflow:

1. **Checkout** — Clone the repository
2. **Setup Node.js** — Install Node.js 18
3. **Install Dependencies** — Run `npm install`
4. **Build** — Compile the Angular app for production
5. **Docker Build** — Build the Docker image
6. **Docker Push** — Push the image to Docker Hub (`marwaguerfel/tekupstudents:latest`)

---

## Project Structure

```
src/
├── app/
│   ├── admin-panel/       # Admin dashboard & student management
│   ├── certification/     # Certification add/view
│   ├── demands/           # Request submission & listing
│   ├── footer/            # Footer component
│   ├── header/            # Header component
│   ├── interfaces/        # TypeScript interfaces/models
│   ├── login/             # Authentication page
│   ├── menu-bar/          # Navigation menu
│   ├── reclamation/       # Complaints submission & listing
│   ├── services/          # API & business logic services
│   ├── side-bar/          # Sidebar navigation
│   ├── student/           # Student panel
│   └── survey/            # Survey module
├── assets/                # Static assets
├── styles.css             # Global styles
└── index.html
```

---

## Angular CLI Reference

| Command | Description |
|---|---|
| `ng serve` | Start dev server |
| `ng build` | Build the project |
| `ng test` | Run unit tests |
| `ng generate component <name>` | Generate a new component |

For more help, run `ng help` or visit the [Angular CLI docs](https://angular.io/cli).
