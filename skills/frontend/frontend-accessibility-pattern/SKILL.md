---

name: frontend-accessibility-pattern
description: Defines accessibility standards for SaaS frontend applications to ensure interfaces are usable by people with diverse abilities and compatible with assistive technologies.
category: frontend
version: 1.0

---

# Frontend Accessibility Pattern

## Purpose

Ensure that SaaS frontend applications are accessible to all users, including those using assistive technologies such as screen readers, keyboard navigation, and alternative input devices.

Accessibility is a fundamental requirement for modern web applications. Without structured accessibility practices, interfaces can become unusable for a significant portion of users.

This skill ensures that AI agents generate frontend systems that follow **accessible UI design principles**, enabling inclusive and compliant user interfaces.

The pattern enforces:

- keyboard navigable interfaces
- proper semantic HTML usage
- accessible form interactions
- screen reader compatibility
- consistent focus management

---

## When to Use This Skill

Use this skill whenever building or modifying frontend UI components.

Typical scenarios include:

- creating interactive UI elements
- building forms
- designing navigation systems
- implementing modal dialogs
- creating data tables
- designing dashboards

Accessibility should be considered in **all user-facing interfaces**.

---

## Core Architectural Principles

### 1. Use Semantic HTML

UI components should use semantic HTML elements whenever possible.

Correct examples:

<button> <nav> <header> <main> <footer> <form> <label> <input> ```

Avoid replacing semantic elements with generic containers such as:

<div>
<span>

when a semantic element is available.

Semantic HTML improves screen reader compatibility and overall accessibility.

2. Keyboard Navigation

All interactive elements must be accessible using keyboard navigation.

Users must be able to interact with the interface using:

Tab

Enter

Space

Arrow keys (when appropriate)

Example expectations:

Tab → move between interactive elements
Enter → activate button
Space → toggle controls

Components must not rely exclusively on mouse interaction.

3. Accessible Form Design

Forms must be fully accessible.

Each input field must be associated with a label.

Example:

<label for="email">Email</label>
<input id="email" type="email" />

Forms should also provide:

clear validation messages

helpful field descriptions

accessible error indicators

Screen readers should clearly announce form fields and errors.

4. Proper ARIA Usage

ARIA attributes should be used when semantic HTML alone cannot describe component behavior.

Examples include:

aria-label

aria-describedby

aria-expanded

aria-live

Example:

<button aria-label="Close modal">

ARIA attributes help assistive technologies understand dynamic UI behavior.

However, ARIA should not replace semantic HTML when native elements are available.

5. Focus Management

Interactive components must properly manage focus.

Common scenarios include:

modal dialogs

dropdown menus

navigation menus

dynamic UI updates

Example modal flow:

User opens modal
↓
Focus moves into modal
↓
User interacts with modal content
↓
Modal closes
↓
Focus returns to triggering element

This ensures smooth navigation for keyboard and screen reader users.

Implementation Guidelines
Always Provide Accessible Labels

All interactive controls must have accessible names.

Example:

<button aria-label="Open settings">

Or visible labels:

<button>Save</button>

Avoid unlabeled icons or controls.

Maintain Logical Tab Order

Interactive elements must follow a logical navigation order.

Example flow:

Header Navigation
↓
Main Content
↓
Form Fields
↓
Actions

Avoid manually manipulating tab order unless necessary.

Ensure Sufficient Color Contrast

Text and UI elements must maintain sufficient contrast for readability.

Avoid color combinations that are difficult to distinguish.

Examples of problematic patterns:

light gray text on white background

low contrast buttons

relying solely on color to convey meaning

Accessible design requires visual clarity.

Provide Accessible Feedback

Dynamic UI updates should provide feedback accessible to assistive technologies.

Examples include:

form validation messages

loading indicators

success notifications

Example:

aria-live="polite"

This allows screen readers to announce updates.

Anti-Patterns

Agents must avoid the following accessibility mistakes.

Clickable Divs

Avoid using generic containers as interactive controls.

Bad example:

<div onClick={handleClick}>

Use proper elements instead:

<button>
Missing Form Labels

Inputs without labels make forms inaccessible.

Bad example:

<input type="email" placeholder="Email">

Instead associate a label element.

Mouse-Only Interactions

Interfaces must not require mouse interaction.

All actions must be accessible via keyboard.

Visual-Only Feedback

Avoid feedback that depends solely on visual cues such as color changes.

Example:

Error messages indicated only by red borders.

Instead provide text feedback.

Expected AI Behavior

When generating frontend UI systems, the AI agent should:

prefer semantic HTML elements

ensure keyboard navigation works across interactive elements

provide accessible form structures

apply ARIA attributes when necessary

maintain proper focus management

Example structure:

components/ui

Button.tsx
Input.tsx
Modal.tsx
Dropdown.tsx
FormField.tsx

Each component should be implemented with accessibility considerations built in.

Example accessibility flow:

Semantic HTML
↓
Accessible Components
↓
Feature Interfaces
↓
Application UI

This ensures the entire frontend system remains accessible and usable for all users.
