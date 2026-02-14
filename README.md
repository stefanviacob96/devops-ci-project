DevOps CI/CD Docker Project

This project demonstrates a complete CI/CD pipeline that automatically builds, tests, and deploys a containerized web application.

When code is pushed to the main branch, the system:
- Builds a Docker image
- Tests the application automatically
- Publishes the image to GitHub Container Registry
- Deploys the new version to a Linux server

This simulates a real-world DevOps workflow where applications are updated automatically after each change.

Technologies Used:
- Docker
- Docker Compose
- GitHub Actions (CI/CD)
- Python (Flask)
- GitHub Container Registry (GHCR)
- Linux server (Multipass VM)
- Self-hosted GitHub Actions runner

How the system works:
Developer pushes code to main
        │
        ▼
GitHub Actions builds and tests the app
        │
        ▼
Docker image is pushed to GHCR
        │
        ▼
Deploy workflow triggers automatically
        │
        ▼
Server pulls the new image
        │
        ▼
Docker Compose restarts the container
Result: the server always runs the latest version of the application.

CI/CD Workflows

1) Build, Test, Push Image
- Runs on every push to main:
  ~ Build Docker image
  ~ Run container
  ~ Perform HTTP smoke test
  ~ Push image to GHCR

2) Automated Deployment
- Runs only after the CI workflow succeeds:
  ~ Pull latest image from GHCR
  ~ Restart container using Docker Compose
- Command used on the server:
  ~ docker compose pull
  ~ docker compose up -d --force-recreate
- Run the application manually:
  ~ docker build -t devops-ci-app .
  ~ docker run -p 5000:5000 devops-ci-app
- Open in browser:
  ~ http://localhost:5000

Aim of the project:
- CI/CD pipeline design
- Automated Docker image builds
- Automated testing in pipelines
- Container registry integration
- Automated deployment to a Linux server
- Self-hosted GitHub Actions runners


    



