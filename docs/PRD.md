# PRD — ISRAA HUB

## 1. Document Overview & Objective
*   **Product Name:** ISRAA Hub.
*   **System Purpose:** The public-facing entry point, educational engine, interactive assessment platform, centralized Algerian regulatory repository, and licensing server for ISRAA.
*   **Primary Objective:** Convert prospective Algerian public/private sector IT leaders (DSI, RSSI) by diagnosing their fragmented IT reality and providing continuous regulatory updates to deployed Core instances.

## 2. Technical Architecture & Stack
*   **Backend Framework:** Django REST Framework (DRF) implementing a strict service-layer architecture (`services.py`).
*   **Frontend Framework:** React SPA styled with Tailwind CSS and headless accessible primitives (no opinionated UI block systems).
*   **Database:** PostgreSQL (Cloud-managed instance).
*   **State Management:** Zustand with automatic synchronization to browser `localStorage` for assessment progress persistence.
*   **Infrastructure:** Containerized microservices (Django API, React SPA, PostgreSQL, Nginx) on a managed container platform.
*   **Shared Contracts:** Versioned data transfer objects and contract definitions consumed via the `@israa/contracts` shared NPM package.

## 3. Epics & User Stories (AI-Ready Specs)
### Epic H1: Interactive Diagnosis & Lead Capture ("Missing Context Map")
*   **US-H1.1 (Interactive Flow):** As an unauthenticated visitor, I want to take a multi-step assessment covering IT assets, regulatory posture (Law 18-07, RNSI), and incident workflows without registering an account.
*   **US-H1.2 (Missing Context Map):** As a user completing the diagnostic, I want to view a visual "Missing Context Map" illustrating organizational disconnects.
*   **US-H1.3 (Lead Ingestion):** As a prospect reviewing my diagnostic results, I want to submit my contact information. Submitting sends a payload to `POST /api/v1/leads/`. The backend must persist the lead and emit a notification webhook to team operations.

### Epic H2: Regulatory Intelligence Feed (Regulatory Watch)
*   **US-H2.1 (Knowledge Base Management):** As an ISRAA Compliance Admin, I need an internal portal to curate Algerian legal frameworks mapped down to structured articles and control objectives.
*   **US-H2.2 (Regulatory Sync API):** As an authorized ISRAA Core instance, I need to call `GET /api/v1/regulatory/updates?since=<timestamp>` using an authorized License Key to pull signed regulatory deltas and control definitions.

### Epic H3: License & Instance Management
*   **US-H3.1 (License Provisioning):** As an ISRAA Operations Engineer, I need an API endpoint to generate cryptographically signed, asset-tiered license keys.
*   **US-H3.2 (License Verification):** As a deployed Core instance, I need to call `POST /api/v1/license/verify` to validate contract status during manual update requests.
