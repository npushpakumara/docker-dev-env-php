![CI](https://github.com/npushpakumara/go-backend-template/actions/workflows/audit.yml/badge.svg)
[![Go Report Card](https://goreportcard.com/badge/github.com/npushpakumara/go-backend-template)](https://goreportcard.com/report/github.com/npushpakumara/go-backend-template)

# Go Backend API template

A clean architecture Go backend template built with Gin, PostgreSQL, GORM, and Uber FX. This project provides a robust starting point for building scalable and maintainable Go applications.

## Features

- Clean architecture with separation of concerns
- RESTful API using the Gin framework
- PostgreSQL database with Gorm ORM
- Dependency injection with Uber FX
- Docker support for easy containerization
- Sending emails using AWS SES and SMTP
- Oauth implementation with Goth

## Getting Started

### Prerequisites

Before you begin, ensure you have met the following requirements:

- [Go](https://golang.org/dl/) version 1.23 or later
- [Docker](https://www.docker.com/get-started) and Docker Compose
- PostgreSQL (if running outside of Docker)

### Project structure

```shell
├── api
│    └── middlewares
│        └── auth.go
├── cmd
│    └── server
│         ├── main.go
│         └── server.go
├── internal
│   ├── aws_client
│   │    └── aws_client.go
│   ├── config
│   │    ├── config.go
│   │    ├── default.go
│   │    └── README.md
│   ├── features
│   │   ├── auth
│   │   │   ├── auth_handler.go
│   │   │   ├── auth_service.go
│   │   │   ├── providers.go
│   │   │   ├── auth_middleware.go
│   │   │   ├── encoder.go
│   │   │   ├── dto
│   │   │   │    ├── request.go
│   │   │   │    └── response.go
│   │   │   └── tokens
│   │   │       └── tokens.go
│   │   ├── email
│   │   │    ├── email_service.go
│   │   │    └── entities
│   │   │         └── email.go
│   │   └── user
│   │       ├── dto
│   │       │    ├── request.go
│   │       │    └── response.go
│   │       ├── entity
│   │       │    └── user.go
│   │       ├── user_handler.go
│   │       ├── user_repository.go
│   │       └── user_service.go
│   └── postgres
│       ├── context.go
│       ├── errors.go
│       ├── utils.go
│       ├── logging.go
│       ├── transactions.go
│       └── postgres.go
├── pkg
│   ├── errors
│   │    └── errors.go
│   ├── logging
│   │    └── logging.go
│   └── validator.go
├── go.mod
├── go.sum
├── Dockerfile
├── docker-compose.yml
├── Makefile
├── README.md
```

### Installation

Refer to `config/default.go` for guidance on setting up environment variables.

```shell
# Clone the project
git clone git@github.com:npushpakumara/go-backend-template.git
cd go-backend-template

# Build docker image
make docker-build

# Run docker compose with postgres
make compose-up
```

## To-do list

- [ ] Add redis caching layer
- [ ] Handle database transactions efficiently
- [ ] Enhance logging capabilities
- [ ] Refine the user module
- [ ] Implement Role-Based Access Control (RBAC) with Casbin
- [x] Add GitHub Actions auditing
- [ ] Implement unit and integration test
- [ ] Add prometheus metrics
