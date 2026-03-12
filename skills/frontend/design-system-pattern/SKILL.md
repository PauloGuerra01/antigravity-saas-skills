---

name: design-system-pattern
description: Defines a structured design system architecture for SaaS frontend applications to ensure visual consistency, reusable UI components, and scalable interface development.
category: frontend
version: 1.0

---

# Design System Pattern

## Purpose

Provide a standardized design system architecture for SaaS frontend applications.

As frontend applications grow, inconsistent UI patterns can quickly emerge if components are created ad-hoc. Different pages may implement buttons, forms, and layouts in inconsistent ways, resulting in fragmented user experiences and difficult-to-maintain UI code.

This skill ensures that AI agents generate frontend systems that implement a **structured design system**, enabling consistent UI development across the entire application.

The pattern enforces:

- centralized reusable UI components
- consistent visual design
- scalable component libraries
- standardized spacing and typography
- predictable interface patterns

---

## When to Use This Skill

Use this skill whenever building or expanding user interface components.

Typical scenarios include:

- building reusable UI elements
- designing application layouts
- implementing forms
- creating dashboards
- structuring design tokens
- scaling UI development across features

All SaaS frontend systems should implement a design system to maintain consistency and reduce UI duplication.

---

## Core Architectural Principles

### 1. Centralized UI Component Library

Reusable UI components should live in a centralized location.

Example structure:


components
└── ui
├── Button.tsx
├── Input.tsx
├── Card.tsx
├── Modal.tsx
├── Dropdown.tsx
└── Badge.tsx


These components act as the foundation of the application's visual system.

They must remain **domain-agnostic** and should not contain business logic.

---

### 2. Consistent Design Tokens

The design system should define reusable visual tokens.

Common tokens include:

- colors
- typography
- spacing
- border radius
- shadows

Example conceptual structure:


styles
└── tokens
├── colors.ts
├── spacing.ts
├── typography.ts
└── shadows.ts


These tokens ensure consistent visual styling across all components.

---

### 3. Component Composition

Complex UI should be composed from smaller design system components.

Example:


DashboardPage
├── PageHeader
├── Card
│ └── Metrics
├── Table
└── Pagination


Higher-level components should rely on foundational UI elements such as buttons, cards, and form inputs.

This promotes consistency and reuse.

---

### 4. Variant-Based Components

UI components should support variants rather than multiple duplicated implementations.

Example:

<Button variant="primary" /> <Button variant="secondary" /> <Button variant="danger" /> ```

Variants allow components to adapt visually while remaining structurally consistent.

5. Separation Between UI and Business Logic

Design system components must focus purely on visual presentation and user interaction.

They must not contain:

API calls

feature-specific logic

business rules

Example separation:

components/ui/Button.tsx

versus

features/billing/components/BillingButton.tsx

The design system provides the base components, while features compose them.

Implementation Guidelines
Build Foundational Components First

Start by implementing foundational UI components.

Typical examples include:

Button

Input

Select

Checkbox

Card

Modal

Tabs

Table

These components should be reusable across all features.

Standardize Layout Patterns

Layouts should follow consistent spacing and structural patterns.

Example:

Page Layout
├── PageHeader
├── Content Section
└── Footer Actions

Standardized layout patterns improve UI predictability.

Use Design Tokens for Styling

Avoid hardcoding styles directly inside components.

Bad example:

style={{ margin: "17px", color: "#3498db" }}

Instead use tokens:

spacing.md
colors.primary

This ensures consistent styling across the application.

Document Component Usage

Reusable UI components should be self-explanatory and easy to adopt.

Components should expose clear props and avoid complex configuration.

Example:

<Button variant="primary" size="md">
  Save Changes
</Button>

Clear APIs encourage reuse across features.

Anti-Patterns

Agents must avoid the following design system mistakes.

Duplicate UI Components

Avoid creating multiple similar implementations of the same UI element.

Bad example:

PrimaryButton
BlueButton
SubmitButton
ActionButton

Instead use a single component with variants.

Hardcoded Styles

Avoid embedding hardcoded colors, spacing, or typography values inside components.

Design tokens should define visual standards.

Business Logic Inside UI Library

The UI library must remain independent of application logic.

Bad example:

Button that triggers billing API logic

UI components should remain generic.

Feature Components Reimplementing UI Elements

Feature modules should not recreate basic UI elements already defined in the design system.

Always reuse the centralized component library.

Expected AI Behavior

When generating frontend UI, the AI agent should:

use components from the centralized UI library

avoid duplicating basic UI elements

follow design tokens for styling

compose complex UI from smaller components

maintain visual consistency across the application

Example structure:

components
└── ui
    ├── Button.tsx
    ├── Input.tsx
    ├── Card.tsx
    ├── Modal.tsx
    └── Table.tsx

features
└── dashboard
    └── components
        ├── MetricsCard.tsx
        └── ActivityTable.tsx

Example UI composition flow:

Design Tokens
↓
UI Components
↓
Feature Components
↓
Application Pages

This architecture ensures a scalable and consistent design system for the entire frontend application.


---

### O que essa skill adiciona ao seu sistema

Essa skill impede um problema **muito comum quando IA gera frontend**: UI inconsistente.

Sem esse padrão, a IA tende a gerar:

- botões diferentes em cada página  
- estilos hardcoded  
- duplicação de componentes  
- UI difícil de manter  

Com essa skill, a IA passa a estruturar:

- **uma biblioteca central de componentes**
- **design tokens reutilizáveis**
- **componentes com variantes**
- **UI consistente em todo o sistema**

Isso cria um frontend **muito mais profissional, escalável e fácil de evoluir**.

---

### Status atual das skills frontend

Criadas:

1. frontend-architecture-pattern  
2. component-design-pattern  
3. state-management-pattern  
4. api-client-pattern  
5. frontend-error-handling-pattern  
6. authentication-flow-pattern  
7. ui-performance-pattern  
8. design-system-pattern  

---

### Faltam **2 skills**

Próximas:

9. **frontend-accessibility-pattern**  
10. **frontend-analytics-pattern**
