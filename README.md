# DevOps CI/CD Docker Project

A simple DevOps project that demonstrates a complete CI/CD pipeline using Docker and GitHub Actions.

The project builds a containerized web application, tests it automatically, and publishes the Docker image to GitHub Container Registry (GHCR).

---

## Technologies Used

- Docker
- GitHub Actions (CI/CD)
- Python (Flask)
- GitHub Container Registry (GHCR)

---

## Project Architecture

1. Developer pushes code to GitHub
2. GitHub Actions pipeline is triggered
3. Docker image is built
4. Container is started and tested automatically
5. Image is pushed to GitHub Container Registry

---

## CI/CD Pipeline Steps

The pipeline runs on every push to the `main` branch and performs:

1. Checkout source code
2. Build Docker image
3. Run container
4. Perform HTTP smoke test
5. Push image to GHCR

---

## Run the Application from the Registry

Anyone can run the application directly from the public container image:

```bash
docker run --rm -p 5000:5000 ghcr.io/stefanviacob96/devops-ci-app:latest

