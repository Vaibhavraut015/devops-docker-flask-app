# DevOps Docker Flask Application

This project showcases a minimal Python Flask web app containerized with Docker, orchestrated locally via Docker Compose, and validated in CI using **GitHub Actions**.

## 📁 Project Structure
```
devops-docker-flask-app/
├── app.py
├── requirements.txt
├── Dockerfile
├── docker-compose.yml
├── README.md
└── .github/
    └── workflows/
        └── ci-cd.yml
```

## 🚀 Run Locally with Docker
Build the image:
```bash
docker build -t devops-docker-app .
```
Run the container:
```bash
docker run -p 5000:5000 devops-docker-app
```
Test it:
```bash
curl http://localhost:5000
```

## 🧰 Run with Docker Compose
```bash
docker compose up --build
```

## 🤖 CI/CD (GitHub Actions)
The workflow at `.github/workflows/ci-cd.yml` performs:
- Checkout
- Docker Buildx setup
- Build image
- Run container and curl health check

## 📦 Requirements
- Docker Engine & Docker Compose (v2)
- Python base image pulls dependencies during build

## 📝 Notes
- Flask binds to `0.0.0.0` so the container port maps to host `localhost:5000`.
- Update the app or pipeline as needed for further demos (K8s, Helm, Terraform, etc.).
```
