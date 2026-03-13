---

name: state-management-pattern
description: Defines how application state should be managed in scalable SaaS frontend systems built with React, Next.js, and TypeScript.
category: frontend
version: 1.0

---

# State Management Pattern

## Purpose

Define a predictable and scalable strategy for managing application state in SaaS frontend systems.

This skill ensures that AI agents generate frontend systems with **clear, maintainable state management patterns** rather than ad-hoc state handling scattered across components.

The goal is to maintain a structured separation between:

* local UI state
* feature-level state
* server state

This prevents common frontend issues such as state duplication, unnecessary global state, and tightly coupled components.

---

# When to Use This Skill

Use this skill whenever:

* managing UI state in React components
* handling shared state between components
* managing asynchronous data from APIs
* structuring feature-level state
* designing scalable frontend architecture

This skill should guide **all state management decisions in the frontend system**.

---

# Core Architectural Principles

## 1. Separate State by Responsibility

Frontend state must be categorized into three primary types:

### Local UI State

State that belongs only to a specific component.

Examples:

* modal visibility
* dropdown state
* input field values
* UI toggles

Example:


const [isOpen, setIsOpen] = useState(false)


Local UI state should remain inside the component.

---

### Server State

Data that originates from the backend.

Examples:

* user profile
* subscription data
* dashboard metrics
* billing information

Server state should be managed using **server-state libraries or dedicated hooks**, not global state.

Example flow:


API → Service → Hook → Component


---

### Shared Feature State

State shared between multiple components within a feature.

Examples:

* dashboard filters
* selected workspace
* active tab state

This state should live in **feature-level hooks or context providers**.

Example:


useDashboardFilters()


Avoid placing feature state in global application stores unless absolutely necessary.

---

## 2. Prefer Local State First

The default choice should always be **local component state**.

Escalate to higher levels only when necessary.

Hierarchy:


Local Component State
↓
Feature-Level State
↓
Global State


Global state should be used sparingly.

---

## 3. Server State Must Not Be Stored in Global Stores

Avoid storing server-fetched data inside global state managers.

Incorrect pattern:


Redux store contains API responses


Preferred pattern:


Service → Hook → Component


Hooks should manage the server state lifecycle.

---

## 4. Encapsulate State Logic in Hooks

State logic should be extracted into custom hooks whenever possible.

Example:


useDashboardMetrics()
useUserProfile()
useBillingHistory()


Hooks allow:

* reusable logic
* cleaner components
* improved testing
* better separation of concerns

Components should **consume hooks**, not manage complex state directly.

---

## 5. Avoid Unnecessary Global State

Global state introduces complexity and tight coupling.

Only use global state for truly global concerns such as:

* authenticated user
* theme configuration
* application settings
* feature flags

Even in these cases, prefer minimal global stores.

---

# Implementation Guidelines

## Keep State Close to Where It Is Used

State should be stored at the **lowest possible level** in the component hierarchy.

Incorrect:


App.tsx manages all application state


Correct:


Feature components manage their own state


This reduces unnecessary re-renders and complexity.

---

## Use Custom Hooks for Shared Logic

If multiple components require the same state logic, extract it into a custom hook.

Example:


hooks/useDashboardFilters.ts
hooks/useUserSession.ts
hooks/useBillingData.ts


Hooks should expose clean interfaces to consuming components.

---

## Avoid Prop Drilling

When passing state through multiple component levels, consider:

* context providers
* feature hooks

Instead of:


App → Layout → Page → Component → Child


Use:


FeatureContext


Only when the state truly belongs to multiple components.

---

## Separate State Logic from UI

State management should live in:


hooks/


UI components should focus on:

* rendering
* user interaction
* layout

Avoid placing complex state logic directly inside UI components.

---

# Anti-Patterns

Agents must avoid the following state management mistakes.

## Global State Overuse

Do not store most application state in global stores.

Bad example:


Redux store managing all application data


This creates unnecessary complexity and tight coupling.

---

## Storing Server Data in Global State

API responses should not be duplicated across the system.

Incorrect:


fetch → store globally → read everywhere


Correct:


fetch → hook → component


---

## Component State Explosion

Avoid components that manage large numbers of state variables.

Example:


component with 15+ useState hooks


Instead extract logic into custom hooks.

---

## State Duplication

Avoid storing the same data in multiple places.

Example:


user data stored in:
component state
global store
feature context


State should have **one clear source of truth**.

---

# Expected AI Behavior

When generating frontend systems, the AI agent should:

* categorize state into local, feature, and global
* keep state close to the components that use it
* encapsulate state logic inside hooks
* avoid unnecessary global state
* separate server state from UI state

Example structure:


features/dashboard/

hooks/
useDashboardMetrics.ts
useDashboardFilters.ts

components/
DashboardPage.tsx
MetricsGrid.tsx
FilterBar.tsx


Hooks manage the state and business logic.

Components focus on rendering UI and handling user interaction.
