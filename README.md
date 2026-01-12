# 📚 Study Group Platform

A centralized study group management platform built with Node.js, TypeScript, Express, PostgreSQL, Redis, and Docker.

[![CI](https://github.com/Tales-Cunha/study-group-platform/actions/workflows/ci.yml/badge.svg)](https://github.com/Tales-Cunha/study-group-platform/actions/workflows/ci.yml)

## 🚀 Quick Start

### Prerequisites

- Docker & Docker Compose
- Node.js 25+ (for local development without Docker)
- Git

### Running Locally with Docker (Recommended)

1. **Clone the repository:**
   ```bash
   git clone https://github.com/Tales-Cunha/study-group-platform.git
   cd study-group-platform
   ```

2. **Create environment file:**
   ```bash
   cp .env.example .env
   ```

3. **Start all services:**
   ```bash
   docker-compose up
   ```

4. **Verify the application:**
   Open http://localhost:3000/health - you should see `{"status":"OK"}`

### Running Locally without Docker

1. **Install dependencies:**
   ```bash
   npm install
   ```

2. **Set up PostgreSQL and Redis:**
   - Ensure PostgreSQL is running on port 5432
   - Ensure Redis is running on port 6379
   - Update `.env` with your database credentials

3. **Start development server:**
   ```bash
   npm run dev
   ```

## 📦 Project Structure

```
study-group-platform/
├── src/                    # Source code
│   ├── index.ts           # Application entry point
│   └── index.test.ts      # Tests
├── dist/                  # Compiled JavaScript (generated)
├── .github/
│   └── workflows/
│       └── ci.yml        # CI/CD pipeline
├── roadmap/              # Project roadmap and documentation
├── docker-compose.yml    # Local development environment
├── Dockerfile           # Multi-stage Docker build
├── tsconfig.json        # TypeScript configuration
├── jest.config.ts       # Test configuration
└── package.json         # Dependencies and scripts
```

## 🏗️ Architecture

### Tech Stack

- **Runtime:** Node.js 25 with TypeScript (strict mode)
- **Framework:** Express 5
- **Database:** PostgreSQL 17
- **Cache:** Redis 7
- **Containerization:** Docker & Docker Compose
- **CI/CD:** GitHub Actions
- **Testing:** Jest with ts-jest
- **Code Quality:** ESLint + Prettier

### Services

| Service | Port | Description |
|---------|------|-------------|
| App | 3000 | Node.js/Express API |
| PostgreSQL | 5432 | Primary database |
| Redis | 6379 | Caching layer |

## 🔧 Environment Variables

All required environment variables are documented in `.env.example`:

```bash
# Application
PORT=3000
NODE_ENV=development

# Database
DB_HOST=localhost
DB_PORT=5432
DB_USER=postgres
DB_PASSWORD=postgres
DB_NAME=study_group_db

# Redis
REDIS_HOST=localhost
REDIS_PORT=6379

# JWT (for authentication - Phase 2)
JWT_SECRET=your_super_secret_jwt_key
JWT_EXPIRES_IN=1h
JWT_REFRESH_SECRET=your_super_secret_refresh_key
JWT_REFRESH_EXPIRES_IN=7d
```

## 🧪 Testing

### Run Tests

```bash
# Run all tests
npm test

# Run tests with coverage
npm run test:coverage

# Run tests in watch mode (development)
npm run test -- --watch
```

### Test Coverage Target

- **Phase 1:** ≥ 70%
- **Final Goal:** ≥ 80%

## 🔍 Code Quality

### Linting and Formatting

```bash
# Run ESLint
npm run lint

# Check code formatting
npm run format:check

# Auto-fix formatting issues
npm run format:fix

# Security audit
npm run audit
```

### Pre-commit Checklist

- ✅ All tests pass
- ✅ No linting errors
- ✅ Code is formatted with Prettier
- ✅ No critical security vulnerabilities

## 🐳 Docker

### Development Build

```bash
docker-compose up --build
```

### Production Build

```bash
# Build production image
docker build --target production -t study-group-platform:prod .

# Run production container
docker run -p 3000:3000 --env-file .env study-group-platform:prod
```

### Multi-stage Build

The Dockerfile uses a 3-stage build:
1. **dev:** Development with hot-reloading
2. **builder:** Compiles TypeScript to JavaScript
3. **production:** Minimal runtime with only production dependencies

## 📊 CI/CD Pipeline

GitHub Actions runs on every push and pull request to `master` and `develop`:

1. **Lint & Audit:** ESLint, Prettier, npm audit
2. **Test:** Jest with coverage reports
3. **Build Docker:** Creates production Docker image
4. **Smoke Test:** Starts services and verifies health endpoint

## 🛣️ Development Roadmap

This project follows a 16-week TDD-driven development roadmap. See [roadmap/ROADMAP.md](./roadmap/ROADMAP.md) for details.

### Current Phase: Phase 1 - Foundation & CI/CD (Weeks 1-2)

**Completed:**
- ✅ Docker & docker-compose setup
- ✅ TypeScript strict mode configuration
- ✅ Express app skeleton with health check
- ✅ GitHub Actions CI/CD pipeline
- ✅ Testing infrastructure (Jest)
- ✅ Code quality tools (ESLint, Prettier)

**In Progress:**
- 🔄 Database schema design & migrations
- 🔄 JWT authentication utilities

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch: `git checkout -b feature/my-feature`
3. Make your changes and ensure tests pass
4. Commit with a meaningful message: `git commit -m "feat: add user authentication"`
5. Push to your fork: `git push origin feature/my-feature`
6. Open a Pull Request

### Commit Message Convention

- `feat:` New feature
- `fix:` Bug fix
- `chore:` Maintenance tasks
- `docs:` Documentation updates
- `test:` Test additions or updates
- `refactor:` Code refactoring

## 📝 License

ISC

## 👥 Author

Tales Cunha ([@Tales-Cunha](https://github.com/Tales-Cunha))

---

**Built with ❤️ following TDD and clean code principles**
