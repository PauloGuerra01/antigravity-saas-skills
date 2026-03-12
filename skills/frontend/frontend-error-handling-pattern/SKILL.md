---

name: frontend-error-handling-pattern
description: Defines a structured approach for handling errors in SaaS frontend applications to ensure predictable UI behavior, consistent user feedback, and reliable debugging.
category: frontend
version: 1.0

---

# Frontend Error Handling Pattern

## Purpose

Provide a consistent and reliable strategy for handling errors in frontend SaaS applications.

Modern frontend systems frequently deal with multiple sources of failure, including API errors, network failures, authentication problems, and unexpected runtime issues. Without a structured error handling strategy, applications can easily become unstable, confusing to users, and difficult to debug.

This skill ensures that AI agents generate frontend systems that implement **predictable and centralized error handling mechanisms**.

The pattern enforces:

- consistent API error handling
- predictable UI error states
- centralized error boundaries
- user-friendly error feedback
- structured logging for debugging

---

## When to Use This Skill

Use this skill whenever the frontend system must handle potential failure scenarios.

Typical cases include:

- API request failures
- form submission errors
- authentication failures
- permission errors
- network connectivity issues
- unexpected runtime exceptions

All user-facing applications must implement structured error handling.

---

## Core Architectural Principles

### 1. Centralized Error Handling for API Requests

Errors originating from backend APIs should be handled in a **centralized layer**, typically inside the API client or service layer.

Example responsibilities:

- normalize error responses
- extract meaningful error messages
- categorize error types (authentication, validation, server errors)

This prevents each component from implementing its own error handling logic.

Example structure:


API Client
↓
Service Layer
↓
Hook
↓
Component


The API client should translate raw HTTP errors into predictable error objects.

---

### 2. UI Error States

Frontend components must handle explicit error states.

Typical UI states include:

- loading state
- success state
- empty state
- error state

Example:


Loading → Success → Error


Components must render appropriate UI feedback depending on the state.

Example UI responses:

- error messages
- retry actions
- fallback components
- notifications

---

### 3. Error Boundaries for Runtime Errors

Unexpected runtime errors in React components should be handled using **error boundaries**.

Error boundaries prevent the entire application from crashing due to a single component failure.

Typical usage:

<ErrorBoundary> <DashboardPage /> </ErrorBoundary> ```

Error boundaries should display fallback UI when failures occur.

4. User-Friendly Error Messaging

Errors displayed to users must be understandable and actionable.

Avoid exposing raw technical errors such as:

500 Internal Server Error

Instead display messages like:

Unable to load your data. Please try again.

User messages should:

explain the issue

suggest a possible action

avoid technical jargon

5. Structured Error Types

Errors should follow predictable structures.

Example error categories:

ValidationError
AuthenticationError
PermissionError
NetworkError
ServerError

Structured error types allow the UI to respond appropriately.

Example:

validation errors → show field messages

authentication errors → redirect to login

network errors → show retry option

Implementation Guidelines
Normalize API Errors

API clients should transform raw HTTP errors into normalized error objects.

Example responsibilities:

extract server messages

attach status codes

categorize error type

This ensures consistent behavior across the application.

Handle Errors Inside Hooks

Hooks responsible for data fetching should expose error states.

Example:

const { data, error, loading } = useDashboardMetrics()

Components should only consume the hook state and render appropriate UI.

Provide Retry Mechanisms

For recoverable failures such as network errors, UI should provide retry actions.

Example:

Retry Button
Reload Data
Try Again

This improves user experience during temporary failures.

Log Errors for Debugging

Errors should be logged for debugging and monitoring purposes.

Possible strategies:

console logging in development

error reporting tools

centralized logging services

This helps teams diagnose production issues.

Anti-Patterns

Agents must avoid the following error handling mistakes.

Ignoring API Errors

Bad example:

fetch("/api/data")

Without handling failure responses.

Every API interaction must include error handling.

Silent Failures

Avoid situations where errors occur but the user receives no feedback.

Bad example:

Application stops updating but no message appears.

Users must always receive feedback when an operation fails.

Raw Technical Errors in UI

Avoid displaying raw backend messages to users.

Bad example:

Error: Request failed with status code 500

Instead display clear user-friendly messages.

Error Logic in UI Components

Components should not contain complex error-handling logic.

Error normalization should occur in the API or service layer.

Expected AI Behavior

When generating frontend systems, the AI agent should:

normalize errors in the API client layer

propagate structured errors through hooks

expose error states to components

implement user-friendly error messages

prevent application crashes using error boundaries

Example architecture:

API Client
↓
Service Layer
↓
Hook
↓
Component

Example feature structure:

features/dashboard

hooks/
useDashboardMetrics.ts

components/
DashboardPage.tsx
DashboardErrorState.tsx

This structure ensures reliable and predictable error handling across the entire frontend system.
