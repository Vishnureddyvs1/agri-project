# 🌾 AgriBazaar - Smart Agriculture E-Commerce & Advisory Platform

> India's smartest multi-vendor agriculture marketplace. Buy seeds, fertilizers, pesticides, equipment. Get AI-powered crop advisory, live weather, mandi prices, and government scheme info.

---

## 🏗️ Architecture

```
agribazaar/
├── backend/          # Node.js + Express REST API
│   ├── prisma/       # Database schema (35+ models)
│   ├── src/
│   │   ├── config/       # Database, Redis, env
│   │   ├── controllers/  # Business logic
│   │   ├── middleware/   # Auth, validation, error handling
│   │   ├── routes/       # 24 API route modules
│   │   └── utils/        # Logger, helpers
│   └── Dockerfile
├── frontend/         # Next.js 14 (App Router) + Tailwind CSS
│   ├── app/          # Pages (Home, Products, Dashboard, Admin, etc.)
│   ├── components/   # Reusable UI components
│   └── lib/          # API client, utilities
├── ai-service/       # Python FastAPI AI microservice
│   ├── main.py       # Disease detection, fertilizer rec, chatbot
│   └── Dockerfile
├── docker-compose.yml
├── .env.example
└── .github/workflows/ci.yml
```

## 🚀 Tech Stack

| Layer | Technology |
|-------|-----------|
| Frontend | Next.js 14, Tailwind CSS, Zustand, Recharts, Socket.io |
| Backend | Node.js, Express.js, Prisma ORM, Socket.io |
| Database | PostgreSQL, Redis (caching) |
| AI Service | Python, FastAPI, scikit-learn |
| Payments | Razorpay (UPI, Cards, Net Banking) |
| DevOps | Docker, GitHub Actions CI/CD |

## 📦 Modules (24 API Endpoints)

| # | Module | Description |
|---|--------|-------------|
| 1 | Auth | JWT/Refresh tokens, OTP, Google OAuth, RBAC |
| 2 | Products | CRUD, search, filtering, reviews, caching |
| 3 | Categories | Tree structure, CRUD |
| 4 | Cart | Add/update/remove, price calculations |
| 5 | Wishlist | Save/remove products |
| 6 | Orders | Full lifecycle: create → track → deliver → return |
| 7 | Payments | Razorpay integration, webhooks, refunds |
| 8 | Users | Profile, addresses, wallet, referrals |
| 9 | Seller | Dashboard, analytics, KYC, payouts |
| 10 | Admin | User/Seller/Product management, analytics |
| 11 | Inventory | Stock tracking, audit logs, low-stock alerts |
| 12 | Advisory | Crop advisory with expert chat (real-time) |
| 13 | Weather | OpenWeatherMap integration, 7-day forecast |
| 14 | Mandi Prices | Live prices from 2500+ mandis, price alerts |
| 15 | Equipment Rental | List & book farm equipment |
| 16 | Marketplace | Farmer-to-farmer crop selling |
| 17 | Community | Forum with posts, replies, expert verification |
| 18 | Blog | CRUD, slugs, view counting |
| 19 | Govt Schemes | PM-KISAN, PMFBY, eligibility check |
| 20 | Notifications | Push + in-app, mark read |
| 21 | Support | Tickets with real-time chat |
| 22 | AI Proxy | Disease detection, fertilizer rec, chatbot |
| 23 | Analytics | Admin/Seller/Farmer analytics |
| 24 | Coupons | Validate, admin CRUD |

## 🔧 Quick Start

### Prerequisites
- Node.js 18+, Docker & Docker Compose, Python 3.11+

### 1. Clone & Configure
```bash
git clone <repo-url> && cd agribazaar
cp .env.example .env
# Edit .env with your credentials
```

### 2. Docker (Recommended)
```bash
docker-compose up -d
# Backend: http://localhost:5000
# Frontend: http://localhost:3000
# AI Service: http://localhost:8000
```

### 3. Manual Setup
```bash
# Backend
cd backend && npm install
npx prisma generate && npx prisma db push
npm run dev

# Frontend
cd frontend && npm install && npm run dev

# AI Service
cd ai-service && pip install -r requirements.txt
uvicorn main:app --reload --port 8000
```

## 🔐 Security
- JWT + Refresh Token rotation
- bcrypt password hashing
- Helmet.js security headers
- Rate limiting (100 req/15min)
- RBAC middleware (Farmer, Seller, Expert, Admin, SuperAdmin)
- Zod request validation

## 🎨 Frontend Pages
- **Home** - Hero, categories, products, AI features, testimonials
- **Products** - Listing with filters, sorting, grid/list view
- **Product Detail** - Gallery, variants, reviews, seller info
- **Login/Register** - Split-panel, role selection, Google OAuth
- **Dashboard** - Farmer dashboard with stats, orders, weather
- **Admin Panel** - Revenue stats, order management, approvals
- **AI Disease Detection** - Upload → analyze → treatment + products
- **Mandi Prices** - Live prices, trends, alerts
- **Weather** - Current + 7-day forecast
- **Crop Advisory** - Expert chat system

## 📄 License
MIT License © 2024 AgriBazaar
