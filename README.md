# cloud-native-devops-platform
Automated CI/CD, Kubernetes, Terraform and Observability

DevOps project designed to demonstrate the complete software delivery lifecycle: application development, Git, CI/CD, Docker, AWS, Terraform, Kubernetes, security, observability, failure recovery, and deployment automation.

# Agenda

Phase 1  → Project foundation + application
Phase 2  → Git + GitHub
Phase 3  → Docker
Phase 4  → AWS infrastructure
Phase 5  → Terraform
Phase 6  → Kubernetes
Phase 7  → CI/CD with GitHub Actions
Phase 8  → Security: SonarQube + Trivy
Phase 9  → Observability: Prometheus + Grafana
Phase 10 → Failure recovery + autoscaling
Phase 11 → Documentation + architecture diagram


# First we need an application that we can containerize and deploy.

For this project, let's use:

Backend: Python + FastAPI
Database: PostgreSQL
Frontend: React later
Containerization: Docker
Cloud: AWS
Registry: Amazon ECR
Orchestration: Kubernetes / EKS
Infrastructure: Terraform
CI/CD: GitHub Actions
Code quality: SonarQube
Security: Trivy
Monitoring: Prometheus + Grafana

Our initial architecture will eventually become:



                    GitHub
                       │
                       ▼
              GitHub Actions
                       │
          ┌────────────┴────────────┐
          │                         │
      Unit Tests                 Security
          │                  SonarQube + Trivy
          │                         │
          └────────────┬────────────┘
                       ▼
                  Docker Build
                       │
                       ▼
                    AWS ECR
                       │
                       ▼
                  AWS EKS
                       │
             ┌─────────┴─────────┐
             │                   │
          API Service        User Service
             │                   │
             └─────────┬─────────┘
                       ▼
                   PostgreSQL
                       │
             ┌─────────┴─────────┐
             ▼                   ▼
         Prometheus           Grafana
