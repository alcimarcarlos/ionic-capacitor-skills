---
name: mobile-performance-and-rendering
description: Optimizes rendering performance in Ionic Angular apps, covering lists, images, detection cycle, and progressive loading. Use when screens show slowness, jank, excessive consumption, or performance regression risk.
---

# mobile-performance-and-rendering

## Objective

Improve interface smoothness and response time on web, Android, and iOS.

## Apply When

- large lists have stuck/janky scroll
- screens have slow visual loading
- memory/cpu consumption is high
- reviewing performance before release

## Mandatory Requirements

- Avoid unnecessary rendering in loops and heavy bindings.
- Apply a loading strategy for images and content.
- Use pagination/virtualization in large lists when appropriate.
- Define perceptible skeleton/loading to reduce perceived wait.
- Measure impact with an objective before/after criterion.

## Recommended Flow

1. Identify the main bottleneck (list, image, change detection, network).
2. Apply optimization at the critical point.
3. Reduce render work per interaction.
4. Validate on a real device when possible.
5. Record gains and residual risks.

## Anti-Patterns (Do Not Do)

- Optimize without measuring a real symptom.
- Load the entire list unnecessarily.
- Re-render components on every global event.
- Ignore performance on lower-capacity devices.

## When to Ask for More Context

- target devices and performance baseline
- average/maximum list and media size
- UX goals (opening time, smooth scroll)
- most critical user flow

## Scope Limits

- covers UI/rendering performance
- does not cover sensitive data security
- does not cover full architecture modeling
- does not define functional UX for filters/list-detail (use `list-detail-search-and-filters`)

## Quick Example (Input -> Output)

Input: "Orders list freezes while scrolling."

Expected output:
- diagnosis of the rendering bottleneck
- pagination/virtualization and binding adjustments
- image/skeleton loading improvement
- simple before/after comparison

## Additional Resources

- For diagnosis and tuning checklist, read `reference.md`.
