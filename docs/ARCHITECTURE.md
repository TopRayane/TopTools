# Architecture

## Public application boundary

This repository owns the public user interface, public application core, reusable tools, local persistence, and public build. It must be independently buildable and testable without access to private infrastructure.

Private company registration, registration notifications, email-provider integration, private endpoints, and deployment secrets are excluded. They belong in the private repository and must remain an optional integration. A client-side flag must never turn the public build into a private-registration build.

## Local-first data model

- Browser structured data: IndexedDB.
- Settings and tool state: local repository APIs over the approved local storage layer.
- Native platform implementations, if introduced later: platform-native storage such as SQLite.
- No cloud database, cloud backup, user sync, or personal telemetry by default.

Each tool must document what it stores, where it stores it, and how the user can inspect, export, or delete it. Schema changes require numbered, tested migrations that preserve existing user data.

## Module contracts

Each tool should expose a manifest containing a unique identifier, name, category, version, inputs, required permissions, and entry point. Tools communicate through documented internal APIs and controlled events. Platform-specific behavior belongs behind adapters.

## Performance

Load only essential startup code. Lazy-load tools where practical. Avoid unnecessary dependencies, polling, heavy main-thread work, repeated DOM updates, and resource leaks. Record bundle size and representative load/operation measurements before making performance claims.

## Diagnostics

Use a central structured logger with debug, info, warn, and error levels. Production logs must not contain personal data, file contents, or secrets. Development diagnostics should make JavaScript, network, storage, and module-loading failures actionable without exposing sensitive values.

## Quality strategy

Build the test system incrementally with unit, integration, end-to-end, regression, accessibility, performance, security, offline, migration, and cross-browser checks. Test data must be synthetic.

## Release boundary

Before a public release, inspect source and generated artifacts for secrets, private endpoints, registration flows, personal data, and company-only code. The public build must not require private services.
