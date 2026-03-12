---

name: api-client-pattern
description: Establishes a standardized API client layer for frontend SaaS applications to ensure consistent, secure, and maintainable communication with backend services.
category: frontend
version: 1.0

---

# API Client Pattern

## Purpose

Provide a structured and centralized method for frontend systems to communicate with backend APIs.

In SaaS applications, frontend systems frequently interact with multiple backend services for authentication, data retrieval, and mutations. Without a standardized API communication layer, applications tend to accumulate scattered network requests, duplicated logic, inconsistent headers, and poor error handling.

This skill ensures that AI-generated frontend systems implement a **centralized API client architecture**, improving reliability, maintainability, and consistency across the application.

The pattern enforces:

- centralized HTTP client configuration
- consistent authentication handling
- reusable API service modules
- predictable request/response handling
- separation between network logic and UI components

---

## When to Use This Skill

Use this skill whenever the frontend system needs to communicate with backend services.

Typical scenarios include:

- fetching user data
- submitting forms
- retrieving dashboard metrics
- interacting with billing systems
- calling authentication endpoints
- integrating third-party APIs

Any HTTP request originating from the frontend should follow this pattern.

---

## Core Architectural Principles

### 1. Centralized API Client

All HTTP communication must go through a **shared API client module**.

Example location:


services/api-client.ts


This module is responsible for configuring:

- base API URL
- default headers
- authentication tokens
- request interceptors
- response interceptors
- standardized error handling

This prevents duplicated configuration across the application.

---

### 2. Service Layer for API Endpoints

API endpoints must be wrapped inside **service functions**.

Example:


services/user-api.ts


Example function:


export async function getUserProfile() {
return apiClient.get("/users/profile")
}


Components should never construct API URLs or handle request logic directly.

---

### 3. Clear Request Naming Conventions

API functions must follow clear and consistent naming patterns.

Examples:


getUserProfile()
updateUserProfile()
createSubscription()
cancelSubscription()


Avoid vague naming such as:


fetchData()
getStuff()


Explicit naming improves readability and maintainability.

---

### 4. Feature-Based API Organization

For larger systems, API services may be organized per feature module.

Example structure:


features
└── dashboard
└── services
└── dashboard-api.ts

features
└── billing
└── services
└── billing-api.ts


This keeps API logic close to the feature domain it belongs to.

---

### 5. Authentication Handling

Authentication headers must be handled automatically by the API client.

Responsibilities include:

- attaching access tokens
- handling expired tokens
- triggering token refresh flows
- handling unauthorized responses

UI components must never manually attach authentication headers.

---

## Implementation Guidelines

### Create a Shared API Client

Create a centralized client module responsible for HTTP communication.

Example responsibilities:

- configure base URL
- attach authentication tokens
- normalize responses
- handle network errors

All service modules should import this client.

---

### Encapsulate Endpoints in Services

Each backend endpoint should be represented by a service function.

Example:


services/dashboard-api.ts

export async function getDashboardMetrics() {
return apiClient.get("/dashboard/metrics")
}


This ensures that endpoint definitions remain centralized.

---

### Use Hooks to Consume API Services

React hooks should be responsible for calling API services and managing state.

Example:


useDashboardMetrics()


Data flow should follow this structure:


API Client
↓
Service
↓
Hook
↓
Component


This separation improves testability and maintainability.

---

## Anti-Patterns

Agents must avoid the following patterns.

### Direct API Calls in Components

Bad example:


useEffect(() => {
fetch("/api/users")
})


Network logic should never live inside UI components.

---

### Hardcoded API URLs

Avoid spreading endpoint URLs throughout the codebase.

Bad example:


fetch("https://api.example.com/users
")


Endpoints should exist only inside service modules.

---

### Authentication Logic in UI

Avoid attaching authentication headers directly inside components.

Bad example:


fetch(url, {
headers: { Authorization: token }
})


Authentication must be handled by the centralized API client.

---

### Duplicate API Logic

Avoid repeating request logic across multiple components.

Always create reusable service functions.

---

## Expected AI Behavior

When generating frontend code that interacts with APIs, the AI agent should:

- create a centralized API client module
- encapsulate endpoints inside service functions
- organize services by feature domain when appropriate
- separate network logic from UI components
- ensure consistent authentication handling

Example structure:


services
└── api-client.ts

features
└── users
└── services
└── user-api.ts

features
└── dashboard
└── services
└── dashboard-api.ts


Data flow:


API Client
↓
Service Layer
↓
Hook
↓
UI Component


This ensures scalable, maintainable API communication across the frontend system.
