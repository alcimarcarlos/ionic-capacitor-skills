# Mobile Agent Governance

You act as a technical agent for hybrid mobile apps.

## Agent Compatibility

This guide is vendor-agnostic and should work with Claude, Cursor, and Codex.

- Treat the instructions in this file as behavioral priority.
- When the platform does not support native "skills", use the `SKILL.md` files as manual playbooks.
- Keep the standard delivery format regardless of the agent.

## Target Stack

- Ionic
- Capacitor
- Angular
- TypeScript
- Laravel API
- token/session authentication according to the backend

## General Rules

- Reply in English.
- Generate code and technical names in English when technically appropriate.
- Prioritize clear architecture, componentization, and predictability.
- Do not invent API contracts. When there is no explicit contract, ask for it or infer it with caveats.
- Do not place complex business rules inside page components.
- Prefer separation by feature/module.
- For native integrations, isolate access in services/adapters.
- Always consider differences between web, Android, and iOS.
- In data flows, prioritize explicit DTOs/interfaces.
- In Ionic screens, prefer Ionic ecosystem components before generic HTML.
- Do not consider screen deliveries complete without covering loading, success, empty, and error states.
- When the API contract is missing, declare the assumption explicitly and mark it as a validation point.
- In features with mobile risk, explain web, Android, and iOS differences in the response.
- Include a minimum test for each critical flow before considering the task complete.

## Standard Delivery Format

When generating a solution, deliver in this order:

1. Objective
2. File structure
3. Code
4. API integration
5. Mobile considerations
6. Tests and validations
7. Assumptions and validation pending items

## Recommended Base Prompt (Multi-Agent)

Use this template when starting tasks in any agent:

```text
Context:
- Stack: Ionic + Capacitor + Angular + TypeScript + Laravel API
- Task objective: <describe>
- Screen/flow: <describe>
- Business rules: <describe>
- Endpoint/payload: <describe or mark as assumption>
- Role/permission: <describe>
- Offline/online impact: <describe>

Delivery instructions:
- Follow AGENTS.md and relevant skills
- Deliver in this format: Objective, File structure, Code, API integration, Mobile considerations, Tests, Assumptions
```

## Mobile Context-Specific Rules

- Assume integration with a Laravel backend.
- Assume frequent need for authentication, listings, and filters.
- Prefer services for API consumption.
- Prefer interceptors for authentication, headers, and common error handling.
- Handle loading, error, empty, and success states in screens.
- When there is risk of offline/intermittent operation, consider local cache and synchronization strategy.

## When to Ask for More Context

Ask for more context when any of the following is missing:

- endpoint
- payload
- business rule
- roles/permissions
- offline behavior
- specific native plugin
