# TopTools

TopTools is an offline-first toolkit designed around privacy, speed, modularity, and maintainability.

## Project principles

- User data, tool records, settings, history, and files remain on the user's device.
- The web edition uses browser-local storage (IndexedDB where structured persistence is needed).
- No cloud synchronization, user profiling, or personal telemetry is enabled by default.
- The public edition contains no company registration flow, private API endpoint, email-delivery integration, or private credentials.
- Core functionality must remain usable without a network connection after required assets have been cached.
- Prefer standards-based HTML, CSS, and JavaScript. Add dependencies only with a documented technical reason.

## Repository boundary

This repository is the public application and reusable public core. Private company-only registration and notification code belongs in [TopTools-private](https://github.com/TopRayane/TopTools-private) and must integrate through a documented, optional boundary. The public build must not be activatable as a private-registration client through a runtime flag or client-side configuration.

## Development

The repository is being initialized. Before adding application code, agree on the module contracts and add executable quality checks alongside the first implementation.

When project scripts are introduced, document their exact commands here, including setup, local development, tests, and production build.

## Documentation

- [Architecture and boundaries](docs/ARCHITECTURE.md)
- [Contribution guide](CONTRIBUTING.md)
- [Security policy](SECURITY.md)

## Privacy

The public application must never upload tool data, local databases, files, settings, or usage history. Review the security and privacy requirements before introducing any network request.
