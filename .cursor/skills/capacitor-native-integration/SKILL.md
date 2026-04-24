---
name: capacitor-native-integration
description: Implements native integrations with Capacitor in a safe, cross-platform way, covering plugins, permissions, lifecycle, and web fallback. Use when there is camera, files, notifications, biometrics, network, or any native API.
---

# capacitor-native-integration

## Objective

Ensure organized, resilient native integration compatible across web, Android, and iOS.

## Apply When

- using a Capacitor plugin
- handling permissions
- creating a native bridge
- handling lifecycle events
- synchronizing web/mobile behavior

## Mandatory Requirements

- Isolate each plugin in a dedicated service/adapter.
- Define a domain interface to reduce coupling with the plugin API.
- Handle permissions explicitly (pre-check, request, and denial).
- Include a web fallback when the functionality allows it.
- Consider `NgZone` when updating UI from a native callback.
- Handle lifecycle (`App.addListener`) when the flow depends on foreground/background.

## Recommended Flow

1. Validate plugin and versions compatible with the target platform.
2. Define an adapter with high-level domain methods.
3. Implement platform guards (`Capacitor.isNativePlatform()`).
4. Implement permission flow with clear states.
5. Handle native exceptions and convert them into domain errors.
6. Validate behavior on web + Android + iOS.

## Anti-Patterns (Do Not Do)

- Call the plugin directly from the screen component.
- Assume the plugin is available on web without a fallback.
- Ignore denied/permanently denied permission state.
- Update UI state without considering Angular zone context.

## Expected Delivery Format

1. Native adapter/service with usage interface.
2. Permission flow and web fallback.
3. Platform notes (Android/iOS/web).
4. Manual device validation checklist.

## When to Ask for More Context

- exact plugin and target version
- target platforms (Android, iOS, web)
- expected behavior when permission is denied
- need to operate offline/foreground/background
- UX requirements (message, retry, action blocking)

## Scope Limits

- covers native APIs and permissions integration
- does not cover DTO/HTTP contract modeling (use `api-data-access-laravel-backend`)
- does not cover broad offline state/sync strategy (use `state-and-offline-mobile`)

## Quick Example (Input -> Output)

Input: "Integrate camera with web fallback and handle denied permission."

Expected output:
- `camera.adapter.ts` with `takePhoto()` and `isAvailable()`
- explicit flow: check permission -> request -> denied/permanent denied
- web fallback with `<input type="file">` or unavailable message
- Android/iOS/web checklist validating success, denial, and cancellation

## Additional Resources

- For permissions and lifecycle guide, read `reference.md`.
