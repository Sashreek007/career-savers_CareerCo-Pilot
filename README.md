<p align="center">
  <img src="https://img.shields.io/badge/Hacked-2026-blueviolet?style=for-the-badge" alt="Hacked 2026" />
  <img src="https://img.shields.io/badge/Status-Actively%20Developed-brightgreen?style=for-the-badge" alt="Status" />
</p>

<h1 align="center"> Talio</h1>

<p align="center">
  <strong>A Unified Career Intelligence Platform</strong>
</p>

---

##  Overview

**Talio** is a unified career platform that brings job discovery, resume generation, application preparation, and interview readiness into one intelligent workspace.

Think of it as a career command center — where you can:

- Discover relevant job opportunities  
- Generate role-specific resumes  
- Prepare tailored applications  
- Practice company-specific interview questions  

All without leaving the platform.

---

## Vision

Talio is designed to optimize for:

> Interview callbacks per 10 applications  
> not application volume.

Instead of blindly applying to hundreds of roles, Talio helps you:

**Find → Tailor → Prepare → Improve**

using structured career data and company-aware insights.

---

## Core Capabilities

- Intelligent Job Discovery  
- AI Resume Generation  
- Application Draft Preparation  
- Company-Specific Interview Prep  
- Feedback-Based Learning Loop  

---

##  Tech Stack

- React + TypeScript  
- FastAPI + Python  
- Gemini AI  
- Playwright  
- SQLite  
- Docker  

---

## Repository Layout

- `packages/` — frontend pnpm workspace (app shell + feature packages + shared libs)
- `backend/` — FastAPI service and tests
- `docs/` — product/design/planning documentation
- `docker-compose.yml` — local multi-service orchestration

---

## Local Commands

- `pnpm install`
- `pnpm build`
- `pnpm typecheck`
- `python3 -m pytest backend/tests`
- `docker compose up --build`

---

##  Note

This project originated from a hackathon build (Hacked 2026) and is now being actively developed independently.

---

## License

This project is licensed under the Career Co-Pilot Protective Open Source License (CC-POL v1.0). See [LICENSE](LICENSE).
