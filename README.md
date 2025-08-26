# 💸 Cashora - AI Payments & Payroll Agent (V1 — RazorpayX Sandbox)

> **AI-powered payments and payroll planner** that ingests payroll/bill files, validates accounts via RazorpayX sandbox, runs risk checks, and generates structured payment plans with LLM reasoning.  
> All payments remain in **sandbox mode (no real money movement)**. Human approvers review, approve, and export manifests with full audit trails and 2FA.

---

## 🚀 Features

- **Payroll ingestion** — Upload CSV/XLS files or API feeds.  
- **RazorpayX sandbox integration** — Beneficiary/account verification, test payouts, and webhook event handling.  
- **AI Planner** — LLM generates structured payment plans with explanations.  
- **Risk engine** — Deterministic rules flag anomalies (amount > limit, duplicate entries, unverified bank).  
- **Approvals workflow** — Dashboard for batch review, item-level evidence, 2FA for high-risk approvals.  
- **Audit logging** — Immutable logs of all uploads, plans, approvals, and connector calls.  
- **Export manifests** — Downloadable CSV/ZIP for manual execution if required.  
- **Secure by design** — RBAC, masked sensitive fields, sandbox-only in V1.  

---


---

## 📦 Tech Stack

- **Backend**: Python 3.11, FastAPI, Alembic, Redis (RQ workers)  
- **Frontend**: React + TypeScript, TailwindCSS (shadcn/ui)  
- **Database**: PostgreSQL + S3 (uploads storage)  
- **LLM**: External LLM API (planner, JSON schema validation)  
- **Payments Sandbox**: RazorpayX Sandbox (test payouts, verification)  
- **Infra**: Docker, GitHub Actions CI/CD  

---

## ⚙️ Setup Instructions

### 1. Clone the repo
```bash
git clone https://github.com/149189/Cashora.git
cd Cashora
```

.env

```
DATABASE_URL=postgresql://user:pass@db:5432/payments
REDIS_URL=redis://redis:6379/0
S3_BUCKET=uploads-bucket
RAZORPAYX_API_KEY=rzp_test_xxxxx
RAZORPAYX_API_SECRET=xxxxx
RAZORPAYX_WEBHOOK_SECRET=whsec_xxxxx
LLM_API_KEY=sk-xxxxx
```
## Run migrations:
alembic upgrade head

## Start backend:
uvicorn app.main:app --reload




