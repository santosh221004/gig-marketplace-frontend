# gig-marketplace-frontend
A responsive, feature-driven React web application for on-demand short-term labor matching. Connects local business managers with verified gig workers for shift-based work, real-time job posting, geofenced shift management, and secure payout workflows.



# ⚡ GigMarketplace Frontend (`gig-marketplace-frontend`)

`gig-marketplace-frontend` is the primary web portal for the On-Demand Gig Marketplace platform. Built with **React**, **TypeScript**, and **Vite**, it serves as the dual-interface portal for **Task Posters** (store managers, event organizers, business owners) and **Gig Workers**.

It interfaces directly with the Spring Boot Microservices ecosystem via the `gig-api-gateway` for authentication, job lifecycle management, geofenced clock-in/clock-out operations, and real-time shift notifications.

---

## 🚀 Key Features

* **Dual-Persona Workflows:**
  * **Business / Poster Portal:** Multi-step job posting wizard, applicant review, live applicant selection, shift approval, and escrow release.
  * **Worker Portal:** Geospatial shift search feed, dynamic rate/distance filtering, instant shift application, and earnings history dashboard.
* **Geofenced Shift Verification:** Mobile-friendly shift check-in and check-out interface backed by browser Geolocation APIs.
* **Real-time Notifications:** WebSocket integration (STOMP/SockJS) for real-time shift alerts, applicant notifications, and approval updates.
* **Role-Based Access Control (RBAC):** Token-based route protection ensuring separation between Worker, Business Manager, and Admin views.

---

## 🛠 Tech Stack

| Category | Technology | Purpose |
| :--- | :--- | :--- |
| **Framework & Build** | React 18+ (Vite) | Lightning-fast development & optimized UI bundle |
| **Language** | TypeScript | Strict type safety matching Spring Boot DTOs |
| **State & Server Sync** | TanStack Query (v5) | API caching, background refetching, & optimistic updates |
| **UI & Styling** | Tailwind CSS + Shadcn UI | Modern, accessible component library |
| **Form Management** | React Hook Form + Zod | Dynamic schema validation & multi-step wizards |
| **HTTP & WebSockets** | Axios + `@stomp/stompjs` | Intercepted REST calls & real-time messaging |

---

## 📁 Feature-Based Directory Architecture

```text
src/
├── app/          # App providers, router setup, and protected routes
├── components/   # Atomic UI primitives (Buttons, Modals, Inputs)
├── features/     # Feature-encapsulated modules
│   ├── auth/     # Login, registration, JWT refresh handlers
│   ├── jobs/     # Job creation wizard, shift feed, filter bars
│   ├── bookings/ # Geofenced shift timer & check-in modals
│   ├── workers/  # Worker profile management & skill verification
│   └── payments/ # Escrow status, earnings, & invoice history
├── pages/        # Top-level route pages (Poster / Worker / Common)
└── services/     # Axios central client & WebSocket connection manager
