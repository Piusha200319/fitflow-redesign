# ADR 0001: Adopt Layered React Native + Node.js/Express + Firebase Architecture for FitFlow Redesign

---

**Status:** Accepted

**Context:** FitFlow requires a rapid redesign to deliver AI personalization, social features, and nutrition tracking across mobile and web platforms with a mid-sized team and limited time-to-market.[cite: 6]

**Decision:** Implement a distinctly tiered software system flow utilizing a React Native Client Layer, an Express.js Gateway & Authentication Layer, and a Node.js Core Backend in the Application Services Layer.[cite: 6] Advanced features will be offloaded to an isolated AI & Advanced Services Layer, supported by a comprehensive Data & Storage Layer featuring Firebase, Redis, and Cloud Storage.[cite: 6]

**Consequences:** Development is accelerated through a shared frontend codebase and clear microservice boundaries.[cite: 6] The system heavily leverages the Firebase ecosystem for authentication, data, and storage, which streamlines deployment but introduces vendor dependency.[cite: 6]

---