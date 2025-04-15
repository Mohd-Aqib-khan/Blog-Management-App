
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
└── Blog-Management-App/
    ├── README.md
    ├── blog-web/
    │   ├── tsconfig.json
    │   ├── .gitignore
    │   ├── README.md
    │   ├── package-lock.json
    │   ├── tsconfig.spec.json
    │   ├── nginx.conf
    │   ├── .dockerignore
    │   ├── Dockerfile
    │   ├── .prettierignore
    │   ├── .editorconfig
    │   ├── angular.json
    │   ├── .prettierrc
    │   ├── package.json
    │   ├── tsconfig.app.json
    │   ├── .vscode/
    │   │   ├── extensions.json
    │   │   ├── launch.json
    │   │   └── tasks.json
    │   └── src/
    │       ├── styles.scss
    │       ├── main.ts
    │       ├── favicon.ico
    │       ├── index.html
    │       ├── environments/
    │       │   ├── environment.prod.ts
    │       │   └── environment.ts
    │       ├── app/
    │       │   ├── app-routing.module.ts
    │       │   ├── app.module.ts
    │       │   ├── app.component.scss
    │       │   ├── app.component.ts
    │       │   ├── app.component.spec.ts
    │       │   ├── app.component.html
    │       │   ├── landing-page/
    │       │   │   ├── landing-page.component.spec.ts
    │       │   │   ├── landing-page.component.scss
    │       │   │   ├── landing-page.component.html
    │       │   │   ├── landing-page.component.ts
    │       │   │   └── components/
    │       │   │       └── trending-blogs/
    │       │   │           ├── trending-blogs.component.spec.ts
    │       │   │           ├── trending-blogs.component.ts
    │       │   │           ├── trending-blogs.component.html
    │       │   │           └── trending-blogs.component.scss
    │       │   ├── dashboard/
    │       │   │   ├── dashboard.module.ts
    │       │   │   ├── dashboard-routing.module.ts
    │       │   │   ├── interface/
    │       │   │   │   └── post.model.ts
    │       │   │   ├── services/
    │       │   │   │   ├── post.service.spec.ts
    │       │   │   │   └── post.service.ts
    │       │   │   └── components/
    │       │   │       ├── post-detail/
    │       │   │       │   ├── post-detail.component.html
    │       │   │       │   ├── post-detail.component.spec.ts
    │       │   │       │   ├── post-detail.component.scss
    │       │   │       │   └── post-detail.component.ts
    │       │   │       ├── add-post/
    │       │   │       │   ├── add-post.component.ts
    │       │   │       │   ├── add-post.component.spec.ts
    │       │   │       │   ├── add-post.component.scss
    │       │   │       │   └── add-post.component.html
    │       │   │       ├── post-list/
    │       │   │       │   ├── post-list.component.ts
    │       │   │       │   ├── post-list.component.spec.ts
    │       │   │       │   ├── post-list.component.scss
    │       │   │       │   └── post-list.component.html
    │       │   │       └── dashboard/
    │       │   │           ├── dashboard.component.scss
    │       │   │           ├── dashboard.component.spec.ts
    │       │   │           ├── dashboard.component.ts
    │       │   │           └── dashboard.component.html
    │       │   ├── models/
    │       │   │   └── api-response.model.ts
    │       │   ├── shared/
    │       │   │   ├── shared.module.ts
    │       │   │   └── components/
    │       │   │       ├── generic-card/
    │       │   │       │   ├── generic-card.component.ts
    │       │   │       │   ├── generic-card.component.html
    │       │   │       │   ├── generic-card.component.spec.ts
    │       │   │       │   └── generic-card.component.scss
    │       │   │       ├── nav-bar/
    │       │   │       │   ├── nav-bar.component.scss
    │       │   │       │   ├── nav-bar.component.ts
    │       │   │       │   ├── nav-bar.component.spec.ts
    │       │   │       │   └── nav-bar.component.html
    │       │   │       └── generic-table/
    │       │   │           ├── generic-table-component.ts
    │       │   │           ├── generic-table-component.spec.ts
    │       │   │           ├── generic-table-component.scss
    │       │   │           └── generic-table-component.html
    │       │   ├── authentication/
    │       │   │   ├── login/
    │       │   │   │   ├── login.component.scss
    │       │   │   │   ├── login.component.html
    │       │   │   │   ├── login.component.ts
    │       │   │   │   └── login.component.spec.ts
    │       │   │   └── sign-up/
    │       │   │       ├── sign-up.component.scss
    │       │   │       ├── sign-up.component.html
    │       │   │       ├── sign-up.component.ts
    │       │   │       └── sign-up.component.spec.ts
    │       │   └── core/
    │       │       ├── interceptors/
    │       │       │   ├── auth.interceptor.ts
    │       │       │   └── auth.interceptor.spec.ts
    │       │       ├── guards/
    │       │       │   ├── auth.guard.spec.ts
    │       │       │   └── auth.guard.ts
    │       │       ├── interfaces/
    │       │       │   └── user.model.ts
    │       │       └── services/
    │       │           ├── auth.service.spec.ts
    │       │           ├── http.service.spec.ts
    │       │           ├── http.service.ts
    │       │           └── auth.service.ts
    │       └── assets/
    │           ├── .gitkeep
    │           ├── images/
    │           │   ├── Image.png
    │           │   ├── Image (1).png
    │           │   ├── Image (2).png
    │           │   └── male-employee-image.png
    │           └── icons/
    │               ├── google.png
    │               └── facebook.png
    ├── .git/
    │   ├── config
    │   ├── packed-refs
    │   ├── HEAD
    │   ├── index
    │   ├── description
    │   ├── hooks/
    │   │   ├── push-to-checkout.sample
    │   │   ├── pre-merge-commit.sample
    │   │   ├── pre-rebase.sample
    │   │   ├── pre-commit.sample
    │   │   ├── commit-msg.sample
    │   │   ├── prepare-commit-msg.sample
    │   │   ├── applypatch-msg.sample
    │   │   ├── pre-receive.sample
    │   │   ├── update.sample
    │   │   ├── pre-push.sample
    │   │   ├── post-update.sample
    │   │   ├── fsmonitor-watchman.sample
    │   │   └── pre-applypatch.sample
    │   ├── info/
    │   │   └── exclude
    │   ├── logs/
    │   │   ├── HEAD
    │   │   └── refs/
    │   │       ├── heads/
    │   │       │   └── main
    │   │       └── remotes/
    │   │           └── origin/
    │   │               └── HEAD
    │   ├── objects/
    │   │   └── pack/
    │   │       ├── pack-310d1f2a0cfd858d0ae81f79a652f7daa27446bf.idx
    │   │       └── pack-310d1f2a0cfd858d0ae81f79a652f7daa27446bf.pack
    │   └── refs/
    │       ├── heads/
    │       │   └── main
    │       └── remotes/
    │           └── origin/
    │               └── HEAD
    ├── k8s/
    │   ├── angular-deployment.yaml
    │   ├── nest-deployment.yaml
    │   └── postgres-deployment.yaml
    └── blog-rest-api/
        ├── tsconfig.json
        ├── tsconfig.build.json
        ├── .gitignore
        ├── README.md
        ├── package-lock.json
        ├── Dockerfile
        ├── eslint.config.mjs
        ├── jest.config.ts
        ├── entrypoint.sh
        ├── nest-cli.json
        ├── .prettierrc
        ├── package.json
        ├── test/
        │   ├── app.e2e-spec.ts
        │   └── jest-e2e.json
        └── src/
            ├── app.module.ts
            ├── app.service.ts
            ├── main.ts
            ├── app.controller.spec.ts
            ├── app.controller.ts
            ├── auth/
            │   ├── auth.controller.spec.ts
            │   ├── jwt.strategy.ts
            │   ├── auth.module.ts
            │   ├── auth.service.spec.ts
            │   ├── auth.service.ts
            │   ├── local.strategy.ts
            │   ├── auth.controller.ts
            │   ├── auth.controller.spec.int.ts
            │   ├── facebook-auth/
            │   │   ├── facebook-auth.service.spec.ts
            │   │   └── facebook-auth.service.ts
            │   ├── google-auth/
            │   │   ├── google-auth.service.ts
            │   │   ├── google-auth.service.spec.ts
            │   │   └── types/
            │   │       └── google-user.type.ts
            │   ├── jwt-auth/
            │   │   ├── jwt-auth.guard.spec.ts
            │   │   └── jwt-auth.guard.ts
            │   └── interfaces/
            │       ├── auth.interface.ts
            │       └── register-request-interface.ts
            ├── database/
            │   └── database.module.ts
            ├── posts/
            │   ├── posts.service.spec.ts
            │   ├── posts.controller.ts
            │   ├── posts.service.ts
            │   ├── posts.module.ts
            │   ├── posts.controller.spec.ts
            │   ├── entities/
            │   │   └── post.entity.ts
            │   └── dto/
            │       ├── update-post.dto.ts
            │       └── create-post.dto.ts
            ├── seed-script/
            │   └── post.seed.ts
            ├── users/
            │   ├── users.controller.spec.ts
            │   ├── users.service.ts
            │   ├── users.controller.ts
            │   ├── users.service.spec.ts
            │   ├── users.module.ts
            │   ├── entities/
            │   │   └── user.entity.ts
            │   └── dto/
            │       ├── create-user.dto.ts
            │       └── update-user.dto.ts
            └── common/
                ├── interfaces/
                │   └── api-response.interface.ts
                └── interceptors/
                    └── response-interceptor/
                        ├── response.interceptor.ts
                        └── response.interceptor.spec.ts

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
kubectl apply -f k8s/angular-deployment.yaml
```

Step 7: Open the application
```
minikube service angular-service
```

## 📦 Future Enhancements

✅ Frontend unit testing

✅ Terraform for AWS EKS/ECR deployment

⏳ Redis caching layer

⏳ WebSocket-based real-time comment updates

⏳ Role-based access control (admin, writer, reader)