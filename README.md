
# Blog-Management-App (Monorepo)

A full-stack, scalable blog management application with OAuth login, CRUD operations for posts, automated testing, and containerized deployment using Docker and Kubernetes (Minikube). Built with NestJS for the backend and Angular for the frontend, this project demonstrates best practices in modern web development and DevOps.


## Features
##🔐 Authentication
Login with Google or Facebook using PassportJS.

JWT-based session management for secure API access.

##📝 Blog Management
Dashboard to manage posts (create, read, update, delete).

Public post detail pages accessible without login.

Frontend built using Angular 18 and Angular Material.

##🧪 Testing & Quality
Unit testing with Jest (Backend) – 70%+ code coverage.

Integration testing with Cypress.

Performance and code quality optimized for scale (1M+ users readiness).

##🚢 Deployment & DevOps
Containerized using Docker.

Deployed via Kubernetes (Minikube).

## Project Directory Structure

```
├── k8s/                      # Kubernetes deployment files
│   ├── postgres-deployment.yaml  # PostgreSQL deployment
│   └── nest-deployment.yaml      # NestJS deployment
├── src/                       # Source code
│   ├── controllers/           # API controllers
│   ├── services/              # Business logic
│   ├── models/                # Database models
│   ├── middleware/            # Authentication middleware
│   └── utils/                 # Helper functions (e.g., JWT handling)
├── Dockerfile                 # Dockerfile for NestJS app
├── docker-compose.yml         # Docker Compose configuration (if needed)
├── package.json               # Dependencies and scripts
├── tsconfig.json              # TypeScript configuration
└── README.md                  # Project documentation
```
## 🚀 Getting Started
# 1. Clone the Repository

```
git clone https://github.com/Mohd-Aqib-khan/blog-management-app.git
cd blog-management-app
```

# 🛠️ Backend Setup (NestJS)
### Environment Variables (apps/blog-rest-api/.env)
```
DB_HOST=postgres
DB_PORT=5432
DB_NAME=blog-db
DB_USER=postgres
DB_PASSWORD=<your_db_password>
PORT=3000
JWT_SECRET=<your_jwt_secret>
JWT_EXPIRES_IN=1d
GOOGLE_CLIENT_ID=<your_google_client_id>
GOOGLE_CLIENT_SECRET=<your_google_client_secret>
FACEBOOK_APP_ID=<your_facebook_app_id>
FACEBOOK_APP_SECRET=<your_facebook_app_secret>
```

### Run Locally

```
cd apps/backend
npm install
npm run start:dev

```
# 🎨 Frontend Setup (Angular)

## Features

Google and Facebook Login

Dashboard for logged-in users

Create Post page (JWT-secured)

Public Post Detail page

Responsive Design + Angular Material + SCSS

## Run Locally
```
cd apps/frontend
npm install --legacy-peer-deps
ng serve
```
## Change baseUrl from environment.ts file (Frontend Repo)
```
baseURL: 'http://localhost:5000',
```
JWT is stored in browser localStorage and attached to each secured API request.
# ☁️ Kubernetes Deployment (Minikube)
Step 1: Install Docker
```

```

Step 2: Install KuberCtl
```
```

Step 3: Install Minikube
```
```

Step 4 Start Minikube
```
minikube start
```

Deploy PostgreSQL
```
kubectl apply -f k8s/postgres-deployment.yaml

```

Step 5: Deploy Backend
```
kubectl apply -f k8s/nest-deployment.yaml

```

Step 6: Deploy Frontend

```
kubectl apply -f k8s/frontend-deployment.yaml
```

## 📦 Future Enhancements

✅ Frontend unit testing

✅ Terraform for AWS EKS/ECR deployment

⏳ Redis caching layer

⏳ WebSocket-based real-time comment updates

⏳ Role-based access control (admin, writer, reader)