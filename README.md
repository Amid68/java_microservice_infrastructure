# Java Microservice Infrastructure

[![Build Status](https://img.shields.io/badge/build-passing-brightgreen)]()
[![Coverage](https://img.shields.io/badge/coverage-85%25-green)]()
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Java Version](https://img.shields.io/badge/Java-17-blue)]()

A production-ready demonstration of modern DevOps practices featuring a Java Spring Boot microservice with complete CI/CD automation, infrastructure as code, and container orchestration.

## 🏗️ Architecture Overview

This project demonstrates a complete DevOps pipeline for a user management microservice, showcasing industry best practices for:

- **Continuous Integration/Continuous Deployment (CI/CD)**
- **Infrastructure as Code (IaC)**
- **Container Orchestration**
- **Monitoring and Observability**
- **Security and Compliance**

## 🚀 Technology Stack

| Category | Technologies |
|----------|-------------|
| **Application** | Java 17, Spring Boot 3.x, PostgreSQL |
| **Containerization** | Docker, Docker Compose |
| **CI/CD** | Jenkins, GitHub Actions |
| **Infrastructure** | Terraform, AWS (ECS, RDS, VPC) |
| **Monitoring** | Prometheus, Grafana, ELK Stack |
| **Security** | OWASP ZAP, Trivy, SonarQube |

## 📋 Features

### Application Features
- ✅ RESTful API for user management
- ✅ JWT-based authentication
- ✅ PostgreSQL database integration
- ✅ Comprehensive test coverage (>85%)
- ✅ OpenAPI 3.0 documentation
- ✅ Health checks and metrics endpoints

### DevOps Features
- ✅ Automated CI/CD pipeline
- ✅ Infrastructure as Code with Terraform
- ✅ Multi-environment deployments (dev/staging/prod)
- ✅ Container security scanning
- ✅ Blue-green deployment strategy
- ✅ Automated rollback capabilities
- ✅ Centralized logging and monitoring

## 🏃‍♂️ Quick Start

### Prerequisites

- Docker and Docker Compose
- AWS CLI configured
- Terraform >= 1.0
- Java 17
- Maven 3.8+

### Local Development

```bash
# Clone the repository
git clone https://github.com/Amid68/java_microservice_infrastructure.git
cd java_microservice_infrastructure

# Start local environment
docker-compose up -d

# Run the application
cd app
./mvnw spring-boot:run

# API will be available at http://localhost:8080
# Swagger UI: http://localhost:8080/swagger-ui.html
```

### Infrastructure Deployment

```bash
# Initialize Terraform
cd infrastructure/terraform/environments/dev
terraform init

# Plan deployment
terraform plan

# Apply infrastructure
terraform apply
```

## 📊 CI/CD Pipeline

The pipeline includes the following stages:

1. **Code Quality** - Static analysis with SonarQube
2. **Testing** - Unit tests, integration tests, and contract tests
3. **Security Scanning** - Dependency and container vulnerability scans
4. **Build & Package** - Maven build and Docker image creation
5. **Deploy to Staging** - Automated deployment to staging environment
6. **Integration Tests** - End-to-end testing in staging
7. **Production Deployment** - Blue-green deployment with manual approval

## 🌍 Infrastructure

### AWS Architecture

```
┌─────────────────┐    ┌──────────────────┐    ┌─────────────────┐
│   Application   │    │    Load          │    │   Database      │
│   Load Balancer │◄───┤    Balancer      ├───►│   (RDS)         │
│   (ALB)         │    │                  │    │   PostgreSQL    │
└─────────────────┘    └──────────────────┘    └─────────────────┘
         │                       │                       │
         ▼                       ▼                       ▼
┌─────────────────┐    ┌──────────────────┐    ┌─────────────────┐
│   ECS Cluster   │    │   VPC & Subnets  │    │   Security      │
│   (Fargate)     │    │   Public/Private │    │   Groups        │
└─────────────────┘    └──────────────────┘    └─────────────────┘
```

### Key Infrastructure Components

- **VPC** with public and private subnets across multiple AZs
- **ECS Fargate** for container orchestration
- **RDS PostgreSQL** with automated backups
- **Application Load Balancer** with SSL termination
- **CloudWatch** for logging and monitoring
- **IAM roles** following least privilege principle

## 📈 Monitoring & Observability

### Metrics & Monitoring
- Application metrics via Micrometer
- Infrastructure monitoring with CloudWatch
- Custom business metrics dashboard
- Automated alerting for critical issues

### Logging
- Centralized logging with ELK stack
- Structured JSON logging
- Log aggregation across all services
- Log retention policies

## 🔒 Security

### Security Measures Implemented
- Container image vulnerability scanning
- Dependency vulnerability checks
- OWASP security testing
- Secrets management with AWS Secrets Manager
- Network security with security groups
- Encrypted data at rest and in transit

## 🧪 Testing Strategy

### Test Types
- **Unit Tests** - 90%+ coverage requirement
- **Integration Tests** - Database and external service integration
- **Contract Tests** - API contract validation
- **End-to-End Tests** - Full user journey testing
- **Performance Tests** - Load and stress testing

### Test Automation
- Automated test execution in CI pipeline
- Test results reporting and trending
- Quality gates for deployment progression

## 📁 Project Structure

```
├── app/                    # Java Spring Boot application
├── infrastructure/         # Terraform IaC modules
├── ci-cd/                 # CI/CD pipeline configurations
├── monitoring/            # Monitoring and alerting setup
├── scripts/               # Automation scripts
└── docs/                  # Project documentation
```

## 🔧 Environment Configuration

| Environment | Purpose | Infrastructure |
|-------------|---------|----------------|
| **Development** | Local development and testing | Docker Compose |
| **Staging** | Pre-production testing | AWS ECS (1 instance) |
| **Production** | Live environment | AWS ECS (3+ instances) |

## 📚 Documentation

- [API Documentation](docs/api-documentation.md)
- [Deployment Guide](docs/deployment-guide.md)
- [Architecture Decision Records](docs/adr/)
- [Runbooks](docs/runbooks/)

## 🤝 Contributing

This project follows standard Git workflow practices:

1. Create feature branch from `main`
2. Implement changes with tests
3. Ensure all CI checks pass
4. Create pull request for review
5. Deploy after approval

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 📞 Contact

For questions about this project's implementation or DevOps practices demonstrated:

- [LinkedIn](https://www.linkedin.com/in/ameed-othman/)
- Email: [othman.ameed@gmail.com]
