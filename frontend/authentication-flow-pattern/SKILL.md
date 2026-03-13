---

name: authentication-flow-pattern
description: Defines a secure and structured authentication flow for SaaS frontend applications, ensuring consistent session management, protected routes, and reliable user authentication behavior.
category: frontend
version: 1.0

---

# Authentication Flow Pattern

## Purpose

Define a secure and predictable authentication flow for SaaS frontend applications.

Authentication is a core component of nearly all SaaS platforms. Without a clear architectural pattern, frontend authentication logic often becomes scattered across components, leading to inconsistent session handling, security vulnerabilities, and unpredictable user behavior.

This skill ensures that AI agents generate frontend systems that implement **structured authentication flows**, including login handling, session persistence, protected routes, and logout mechanisms.

The pattern enforces:

- centralized authentication logic
- predictable session management
- protected application routes
- secure token handling
- clear authentication states

---

## When to Use This Skill

Use this skill whenever the frontend application must manage authenticated users.

Typical scenarios include:

- login and logout flows
- session persistence
- protected application pages
- retrieving authenticated user data
- handling token expiration
- redirecting unauthenticated users

All SaaS frontend systems with user accounts should implement this pattern.

---

## Core Architectural Principles

### 1. Centralized Authentication Logic

Authentication logic must be centralized in a dedicated authentication module.

Example location:


features/auth


Example structure:


features/auth
├── hooks
│ └── useAuth.ts
├── services
│ └── auth-api.ts
├── context
│ └── auth-context.tsx
└── types
└── auth.types.ts


Authentication responsibilities should not be scattered across unrelated components.

---

### 2. Authentication State Management

The application must maintain a global authentication state representing the user's session.

Typical states include:


unauthenticated
authenticating
authenticated
session-expired


Example flow:


Login → Token Received → Session Stored → Authenticated State


The authentication state should be accessible across the application.

---

### 3. Session Persistence

Authenticated sessions should persist across page reloads.

Typical strategies include storing authentication tokens in:

- HTTP-only cookies
- secure browser storage
- session storage (when appropriate)

The frontend must restore authentication state when the application initializes.

Example initialization flow:


App Load
↓
Check Existing Session
↓
Validate Token
↓
Restore Auth State


---

### 4. Protected Routes

Certain pages in SaaS applications require authenticated access.

Protected routes must enforce authentication checks.

Example:


/dashboard
/billing
/account


If a user is not authenticated, they should be redirected to the login page.

Example flow:


User requests /dashboard
↓
Check auth state
↓
If not authenticated → redirect to /login


This prevents unauthorized access to private application areas.

---

### 5. Token Expiration Handling

Authentication tokens may expire and must be handled gracefully.

The frontend should detect expired tokens and respond appropriately.

Example strategies:

- refresh tokens automatically
- redirect users to login
- clear invalid sessions

Example flow:


API Request
↓
Token Expired
↓
Refresh Token Attempt
↓
If refresh fails → logout user


---

## Implementation Guidelines

### Centralize Auth Hooks

Authentication logic should be exposed through reusable hooks.

Example:


useAuth()


Typical hook responsibilities:

- retrieve current user
- check authentication status
- handle login
- handle logout

Components should rely on these hooks instead of implementing authentication logic directly.

---

### Keep Login Logic in Services

Authentication API calls should live in service modules.

Example:


features/auth/services/auth-api.ts


Example functions:


loginUser()
logoutUser()
refreshSession()
getCurrentUser()


This keeps network logic separate from UI behavior.

---

### Protect Pages Using Auth Guards

Pages that require authentication should use route protection mechanisms.

Example pattern:

<AuthGuard> <DashboardPage /> </AuthGuard> ```

Auth guards should verify authentication before rendering protected content.

Logout Must Clear Session State

Logging out must fully reset the user's authentication state.

Example responsibilities:

remove stored tokens

clear user data

reset auth state

redirect to login page

Incomplete logout flows can create security risks.

Anti-Patterns

Agents must avoid the following authentication mistakes.

Authentication Logic Inside UI Components

Bad example:

component directly checks localStorage token

Authentication logic should live in centralized modules.

Token Handling Spread Across Components

Avoid manually attaching tokens in multiple places.

Token management should be handled by the API client.

Inconsistent Route Protection

Some protected routes checking authentication while others do not.

All private application areas must enforce authentication.

Ignoring Token Expiration

Failing to handle expired tokens leads to broken sessions and poor user experience.

Token expiration must trigger a recovery flow.

Expected AI Behavior

When generating authentication systems, the AI agent should:

centralize authentication logic in a dedicated auth module

expose authentication state through hooks or context

implement protected routes

manage session persistence

properly handle login, logout, and token expiration

Example structure:

features/auth

hooks/
useAuth.ts

services/
auth-api.ts

context/
auth-context.tsx

types/
auth.types.ts

Example authentication flow:

Login Page
↓
Authentication Request
↓
Receive Token
↓
Store Session
↓
User Authenticated
↓
Access Protected Routes

This architecture ensures a secure and predictable authentication experience across the frontend application.
