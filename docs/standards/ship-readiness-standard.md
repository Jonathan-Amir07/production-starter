# Ship-Readiness Specification Standard (Security, Privacy & Production)

This standard defines the pre-implementation quality bar for any feature, API route, database schema, or deployment change. A fresh Goldfish reviewer audits the specification or plan against these rules before code is written.

## Core Principle

A design passes only if an unfamiliar engineer can verify that every new route, data store, third-party integration, and UI flow is secure by default, legally compliant for user data, performant under load, and observable in production.

## Mandatory Audit Gates

### 1. Authentication, Authorization & Mutability
- Every endpoint or handler must specify its HTTP method(s), caller identity, and authorization rule.
- **Blocker**: State mutations triggered by unauthenticated `GET` requests, missing ownership checks (IDOR), or wildcard CORS (`*`) paired with credentials.
- **Blocker**: Client-side checks without matching server-side enforcement or database Row-Level Security (RLS).

### 2. Data Privacy, Consent & Lifecycle (GDPR / Legal)
- Any feature collecting PII (emails, names, IPs, tokens, analytics) must state:
  - What data is stored and why
  - Retention window and user deletion path
  - Which third-party processors (DPAs) receive the data
- **Blocker**: Non-essential trackers or third-party cookies firing prior to explicit user consent.

### 3. Abuse Resistance & Secrets Hygiene
- Public forms and APIs must specify input validation limits, escaping/sanitization, and rate-limiting strategy (explicitly noting whether serverless cold starts bypass in-memory limiters).
- All secrets must live in server environment variables and `.env.example` placeholders—never embedded in client bundles or committed `.env` files.

### 4. Performance, Failure Modes & Rollback
- Designs involving database queries or asset delivery must address indexing/pagination, payload caching, render-blocking scripts, and graceful degradation when third-party APIs fail or time out.
- Every external dependency must define failure behavior (timeout, fallback response, error logging without leaking stack traces or private keys).

### 5. Discoverability & Repo Hygiene (Web Launches)
- Public web surfaces must specify canonical URLs, `robots.txt`/`sitemap.xml` impact, HTTP security headers (`vercel.json`/middleware), and CI build/test checks.
