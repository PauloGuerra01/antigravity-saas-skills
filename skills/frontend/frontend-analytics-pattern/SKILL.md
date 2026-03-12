---

name: frontend-analytics-pattern
description: Defines how SaaS frontend applications should implement analytics tracking to measure user behavior, product usage, and feature adoption.
category: frontend
version: 1.0

---

# Frontend Analytics Pattern

## Purpose

Define a structured approach for collecting product analytics and user behavior data in SaaS frontend applications.

Analytics is critical for understanding how users interact with a product, identifying usability issues, measuring feature adoption, and guiding product decisions.

Without a standardized analytics implementation, tracking logic becomes inconsistent and scattered across the codebase, making data unreliable and difficult to maintain.

This skill ensures that AI agents generate frontend systems that implement **structured, centralized analytics tracking**.

The pattern enforces:

- centralized analytics tracking logic
- consistent event naming conventions
- separation between UI logic and analytics tracking
- scalable tracking architecture
- reliable product usage insights

---

## When to Use This Skill

Use this skill whenever the frontend application needs to track user behavior or product usage.

Typical scenarios include:

- page views
- feature usage tracking
- user interactions
- form submissions
- onboarding progress
- conversion events

All SaaS platforms should implement analytics to understand user behavior and improve product development.

---

## Core Architectural Principles

### 1. Centralized Analytics Module

All analytics tracking should be centralized in a dedicated analytics module.

Example location:


lib/analytics


Example structure:


lib
└── analytics
├── analytics-client.ts
├── track-event.ts
└── analytics-types.ts


This module is responsible for:

- sending events to analytics providers
- standardizing event structures
- managing analytics integrations

UI components should never communicate directly with analytics providers.

---

### 2. Event-Based Tracking

Analytics should follow an **event-based tracking model**.

Example events include:


user_logged_in
dashboard_viewed
subscription_created
feature_used
settings_updated


Events should describe meaningful user actions within the product.

Each event may include contextual metadata.

Example:


trackEvent("feature_used", {
feature: "export_report"
})


---

### 3. Consistent Event Naming

Event names must follow a consistent naming convention.

Recommended format:


object_action


Examples:


user_signed_up
user_logged_in
dashboard_viewed
report_generated
subscription_cancelled


Consistent naming ensures analytics data remains readable and organized.

---

### 4. Track Meaningful Product Signals

Analytics should focus on meaningful product insights.

Examples include:

- onboarding completion
- key feature usage
- conversion events
- engagement metrics
- retention indicators

Avoid tracking excessive low-value events.

Analytics should prioritize signals that inform product decisions.

---

### 5. Separation from UI Components

Analytics tracking must be separated from UI logic.

Bad example:


component directly calls analytics provider


Correct structure:


UI Component
↓
Analytics Helper
↓
Analytics Client
↓
Analytics Provider


This separation allows analytics providers to change without affecting UI code.

---

## Implementation Guidelines

### Create an Analytics Client

Implement a centralized analytics client responsible for sending events.

Example file:


lib/analytics/analytics-client.ts


Responsibilities include:

- initializing analytics providers
- sending tracking events
- managing provider configuration

---

### Implement a Track Event Helper

Expose a simple function used across the application.

Example:


trackEvent(eventName, metadata)


This helper ensures all events follow the same structure.

Example usage:


trackEvent("dashboard_viewed")


or


trackEvent("report_generated", {
reportType: "sales"
})


---

### Track Key User Interactions

Analytics should capture meaningful user behavior.

Examples include:

- navigation between pages
- feature usage
- user onboarding steps
- account upgrades
- subscription actions

These signals help product teams understand product usage.

---

### Avoid Overtracking

Do not track every minor UI interaction.

Focus on events that provide useful product insights.

Examples of low-value events:

- button hover
- trivial UI state changes

Tracking should remain intentional and meaningful.

---

## Anti-Patterns

Agents must avoid the following analytics implementation mistakes.

### Direct Provider Calls in Components

Bad example:


analytics.track("button_clicked")


Components should instead call a centralized helper.

---

### Inconsistent Event Naming

Avoid inconsistent event names such as:


login
userLogin
LoginClicked


Use standardized naming conventions.

---

### Analytics Logic Inside UI Components

Tracking logic should remain separate from UI behavior.

Analytics modules should handle event processing.

---

### Tracking Sensitive Data

Avoid sending personally identifiable or sensitive user data.

Examples of data that should not be tracked:

- passwords
- authentication tokens
- sensitive personal information

Analytics data should remain privacy-conscious.

---

## Expected AI Behavior

When generating frontend systems, the AI agent should:

- create a centralized analytics module
- implement standardized event tracking
- use consistent event naming conventions
- separate analytics logic from UI components
- track meaningful product interactions

Example structure:


lib
└── analytics
├── analytics-client.ts
├── track-event.ts
└── analytics-types.ts


Example usage flow:


User Interaction
↓
trackEvent()
↓
Analytics Client
↓
Analytics Provider


This architecture ensures consistent and scalable analytics tracking across the SaaS frontend system.
