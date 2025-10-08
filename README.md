# 🔥 Etincel - AI-Powered Dating Platform

[![License](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Node.js](https://img.shields.io/badge/node-20%2B-brightgreen)](https://nodejs.org)
[![Docker](https://img.shields.io/badge/docker-24%2B-blue)](https://www.docker.com)
[![MongoDB](https://img.shields.io/badge/mongodb-7.0-green)](https://www.mongodb.com)

Complete, production-ready dating platform with AI matching, blockchain verification, real-time features, and comprehensive monetization.

## ✨ Key Features

- 🤖 **AI-Powered Matching** with NLP compatibility scoring
- ⛓️ **Blockchain Verification** via Polygon NFTs
- 💬 **Real-Time Chat** with Socket.IO
- 📹 **Video Calls** via WebRTC
- 📍 **GPS Location** matching with Redis Geo
- 💳 **Complete Monetization** (Stripe + ETI Tokens)
- 🔐 **Biometric Auth** (Face ID + Fingerprint)
- 🌍 **Multi-Platform** (iOS, Android, Web)
- 🌐 **I18n Support** (20+ languages)

## 🚀 Quick Start

### Prerequisites

- **Node.js** 20+
- **Docker** & Docker Compose
- **MongoDB** 7.0+
- **Redis** 7+
- **Go** 1.21+ (for location service)
- **Python** 3.11+ (for AI service)

### One-Command Setup

```bash
# Clone repository
git clone https://github.com/yourorg/etincel.git
cd etincel

# Complete setup (installs dependencies, sets up DB, generates Prisma clients)
make setup

# Seed database with test data
make db-seed

# Start development environment
make dev
```

### Access Applications

- **Desktop Web**: http://localhost:3000
- **Mobile Web**: http://localhost:5173
- **Admin Dashboard**: http://localhost:3100
- **API Docs**: http://localhost:8000
- **MinIO Console**: http://localhost:9001
- **Grafana**: http://localhost:3300

## 📖 Documentation

- **Setup Guide**: See below
- **API Documentation**: `/docs/API.md`
- **Architecture**: `/docs/ARCHITECTURE.md`
- **Deployment**: `/docs/DEPLOYMENT.md`

## 🛠️ Development

### Available Commands

```bash
make help                 # Show all available commands
make install              # Install all dependencies
make dev                  # Start development environment
make test                 # Run all tests
make logs                 # View service logs
make health               # Check service health
```

### Working with Individual Services

```bash
# Start specific service
cd services/auth-service
npm run dev

# View logs
make logs-service SERVICE=auth-service

# Restart service
make restart-service SERVICE=auth-service
```

### Database Operations

```bash
make db-init              # Initialize MongoDB
make db-migrate           # Run migrations
make db-seed              # Seed test data
make db-shell             # Open MongoDB shell
make db-backup            # Create backup
```

## 🗄️ Prisma & Database

### Generate Prisma Clients

```bash
make prisma-generate      # Generate all Prisma clients
```

### Push Schemas to MongoDB

```bash
make prisma-push          # Push all schemas
```

### Open Prisma Studio

```bash
make prisma-studio SERVICE=auth-service
```

## 🧪 Testing

```bash
make test                 # Run all tests
make test-unit            # Unit tests only
make test-e2e             # E2E tests
```

## 🚀 Production Deployment

### Docker Deployment

```bash
make build                # Build all images
make prod                 # Start production
```

### Ubuntu Server

```bash
# Run setup script
bash scripts/setup-ubuntu.sh

# Configure environment
nano .env.production

# Deploy
make deploy
```

### SSL Setup

```bash
sudo certbot --nginx -d etincel.app -d www.etincel.app
```

## 📊 Monitoring

- **Prometheus**: http://localhost:9090
- **Grafana**: http://localhost:3300 (admin/admin)
- **Health Checks**: `make health`

## 🔒 Security

- HTTPS/TLS encryption
- JWT authentication
- OAuth2 (Google, Facebook, Apple)
- Rate limiting
- Input validation
- GDPR/CCPA compliant

## 💰 Monetization

- **Freemium**: 100 free likes/day
- **Premium**: $9.99/month
- **Gold**: $19.99/month
- **In-App Purchases**: Boosts, Super Likes, Gifts
- **ETI Tokens**: Crypto payments with 15% platform fee
- **AdMob**: Banner, interstitial, rewarded ads

## 📱 Mobile Development

```bash
cd client/mobile-native
npm run ios              # Run on iOS
npm run android          # Run on Android
```

## 🤝 Contributing

1. Fork the repository
2. Create feature branch (`git checkout -b feature/amazing`)
3. Commit changes (`git commit -m 'Add amazing feature'`)
4. Push to branch (`git push origin feature/amazing`)
5. Open Pull Request

## 📄 License

MIT License - see [LICENSE](LICENSE)

## 💬 Support

- **Email**:# 🔥 Etincel - Complete Production-Ready Source Code

## 📁 COMPLETE FILE STRUCTURE

```
etincel/
├── 📄 .env.example
├── 📄 .env.production
├── 📄 .gitignore
├── 📄 package.json
├── 📄 Makefile
├── 📄 README.md
├── 📄 LICENSE
├── 📄 docker-compose.yml
├── 📄 docker-compose.dev.yml
├── 📄 nginx.conf
│
├── 📁 prisma/
│   └── 📄 schema.prisma (Master)
│
├── 📁 services/
│   ├── 📁 auth-service/
│   │   ├── 📄 package.json
│   │   ├── 📄 tsconfig.json
│   │   ├── 📄 Dockerfile
│   │   ├── 📄 .env.example
│   │   ├── 📁 prisma/
│   │   │   └── 📄 schema.prisma
│   │   └── 📁 src/
│   │       ├── 📄 main.ts
│   │       ├── 📁 controllers/
│   │       │   └── 📄 auth.controller.ts
│   │       ├── 📁 services/
│   │       │   ├── 📄 auth.service.ts
│   │       │   ├── 📄 oauth.service.ts
│   │       │   └── 📄 redis.service.ts
│   │       ├── 📁 routes/
│   │       │   ├── 📄 auth.routes.ts
│   │       │   └── 📄 oauth.routes.ts
│   │       ├── 📁 middleware/
│   │       │   ├── 📄 auth.middleware.ts
│   │       │   └── 📄 errorHandler.ts
│   │       └── 📁 dtos/
│   │           └── 📄 auth.dto.ts
│   │
│   ├── 📁 profile-service/ (same structure)
│   ├── 📁 match-service/
│   ├── 📁 chat-service/
│   ├── 📁 payment-service/
│   ├── 📁 notification-service/
│   ├── 📁 media-service/
│   ├── 📁 analytics-service/
│   ├── 📁 blockchain-service/
│   ├── 📁 webrtc-service/
│   ├── 📁 location-service/ (Go)
│   │   ├── 📄 go.mod
│   │   ├── 📄 go.sum
│   │   ├── 📄 main.go
│   │   └── 📄 Dockerfile
│   └── 📁 ai-service/ (Python)
│       ├── 📄 requirements.txt
│       ├── 📄 Dockerfile
│       └── 📁 app/
│           └── 📄 main.py
│
├── 📁 client/
│   ├── 📁 mobile-native/
│   │   ├── 📄 package.json
│   │   ├── 📄 app.json
│   │   ├── 📄 App.tsx
│   │   └── 📁 src/
│   ├── 📁 mobile-web/
│   │   ├── 📄 package.json
│   │   ├── 📄 vite.config.ts
│   │   ├── 📄 index.html
│   │   └── 📁 src/
│   └── 📁 desktop-web/
│       ├── 📄 package.json
│       ├── 📄 next.config.js
│       └── 📁 app/
│
├── 📁 admin-dashboard/
│   ├── 📄 package.json
│   ├── 📄 tsconfig.json
│   ├── 📄 vite.config.ts
│   ├── 📄 Dockerfile
│   └── 📁 src/
│       ├── 📄 App.tsx
│       ├── 📁 pages/
│       ├── 📁 components/
│       └── 📁 services/
│
├── 📁 scripts/
│   ├── 📄 setup-ubuntu.sh
│   ├── 📄 deploy.sh
│   ├── 📄 backup.sh
│   ├── 📄 restore.sh
│   ├── 📄 health-check.sh
│   ├── 📄 setup-prisma.sh
│   ├── 📄 migrate-all.sh
│   ├── 📄 init-mongodb.sh
│   ├── 📄 check-prisma.sh
│   └── 📄 seed-db.ts
│
├── 📁 infra/
│   ├── 📁 k8s/
│   │   ├── 📁 deployments/
│   │   ├── 📁 services/
│   │   └── 📁 ingress/
│   └── 📁 terraform/
│
└── 📁 monitoring/
    ├── 📁 prometheus/
    │   └── 📄 prometheus.yml
    └── 📁 grafana/
        └── 📁 dashboards/