# FitFlow Redesign

---

## Project Overview

FitFlow is a fitness tracking application redesign based on a human-centered design case study. The redesign focuses on addressing common user problems in fitness tracking applications and introduces features to provide a more engaging, personalized, and convenient experience.

The redesign addresses the following key problems:

- **Personalization gap** — Addressed through AI-powered personalized workout plans.
- **Social isolation** — Addressed through social community and challenge features.
- **High friction in daily tracking** — Reduced through streamlined fitness and activity tracking.
- **Lack of motivation and celebratory elements** — Addressed through engaging progress dashboards, achievements, and social features.
- **Nutrition tracking friction** — Improved through computer vision and nutrition photo recognition.

---

## Project Objectives

The primary objective of the redesign is to create a more engaging, personalized, and socially connected fitness tracking experience that reduces user friction and encourages long-term motivation and consistency.

---

## Selected Technology Stack

| Component | Technology | Purpose |
|---|---|---|
| Frontend | React Native | Cross-platform mobile application for iOS and Android |
| Web | React Native Web | Web compatibility using the same codebase |
| Backend | Node.js + Express.js | Core API and backend services |
| Database | Firebase Firestore + Realtime Database | Primary NoSQL datastore and real-time social features |
| Authentication | Firebase Authentication | Secure user identity and sign-in management |
| AI/ML | TensorFlow Lite + Cloud ML | On-device personalization and advanced recommendation models |
| Computer Vision | ML Kit / Computer Vision Service | Nutrition photo recognition and food analysis |
| Cache | Redis | Server-side caching and performance optimization |
| Storage | Firebase Cloud Storage | Storing user media and application assets |
| Analytics | Firebase Analytics + Crash Reporting | User behavior tracking and application stability monitoring |
| Offline Support | SQLite | Client-side offline data storage and synchronization |

**Note:** PostgreSQL/Supabase may be used optionally as a secondary database for relational reporting and advanced analytical requirements.

---

## Architecture Overview

The system follows a modern, decoupled architecture in which the React Native client communicates with an **Express.js API Gateway**. The API Gateway connects to backend services responsible for different application functions.

The architecture includes specialized services for:

- User authentication and account management
- Fitness and activity tracking
- AI-powered workout recommendations
- Computer vision for nutrition recognition
- Social community and challenge features
- Notifications and real-time interactions
- Data storage and synchronization
- Analytics and performance monitoring

For full details, please see the **High-Level Architecture documentation**.

---

## Repository Structure

```text
fitflow-redesign/
├── README.md
├── .gitignore
│
├── frontend/
├── backend/
├── ai-service/
│
├── docs/
│   ├── technology-comparison.md
│   ├── decision-matrix.md
│   ├── architecture.md
│   ├── ADR.md
│   └── architecture-diagram.png
│
└── docs/
    └── report/
        └── README.md
