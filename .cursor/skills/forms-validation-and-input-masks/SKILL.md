---
name: forms-validation-and-input-masks
description: Implements mobile forms with robust validation, masks, and consistent error UX in Ionic Angular. Use when creating or refactoring signup, login, profile, filter screens, and any user data input.
---

# forms-validation-and-input-masks

## Objective

Standardize forms with validation, masks, and clear feedback to reduce input errors and rework.

## Apply When

- creating a signup/login/profile form
- validating required fields and formats
- applying phone, document, currency, or date masks
- improving submit experience and error messages

## Mandatory Requirements

- Use `ReactiveForms` for forms with business rules.
- Validate on the client with clear messages per field.
- Handle backend validation (`422`) with field mapping.
- Block invalid submit and show submission state.
- Apply masks only when they improve UX and do not break accessibility.

## Recommended Flow

1. Define the field contract (type, requiredness, format).
2. Create `FormGroup` with synchronous/asynchronous validators.
3. Implement masks and input normalization.
4. Map local and remote errors to consistent messages.
5. Validate the complete flow: fill, error, correction, and submit.

## Anti-Patterns (Do Not Do)

- Validate only on the backend without immediate feedback.
- Show raw technical errors to the end user.
- Allow multiple parallel submits.
- Use a mask that changes the value without controlled parsing.

## When to Ask for More Context

- required fields and rules for each field
- format expected by the backend (masked or clean value)
- field error and global error behavior
- need for asynchronous validation (for example: unique email)

## Scope Limits

- covers form UX, validation, and data input
- does not cover navigation between screens (use `ionic-angular-architecture`)
- does not cover full HTTP contracts (use `api-data-access-laravel-backend`)

## Quick Example (Input -> Output)

Input: "Signup screen with name, phone, and email."

Expected output:
- `FormGroup` with validators (`required`, `email`, `minLength`)
- phone mask with clean value persistence
- `422` handling mapped by field
- submit button with `loading` state and double-click blocking

## Additional Resources

- For validation matrix and message pattern, read `reference.md`.
