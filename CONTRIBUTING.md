# Contributing

## Before implementation

1. Clarify the user problem and acceptance criteria.
2. Assess privacy, security, performance, offline behavior, accessibility, and platform impact.
3. Define the module contract and ownership boundary.
4. Design tests before or alongside implementation.

## Engineering standards

- Prefer semantic HTML, standard CSS, and modular JavaScript.
- Avoid unnecessary frameworks, dependencies, network calls, and abstractions.
- Keep tools independent; failure in one tool must not disable the whole application.
- Use documented internal APIs and controlled events rather than reaching into another module's internals.
- Keep Persian/English localization separate from UI logic and implement real RTL/LTR behavior.
- Follow system theme by default.
- Release resources and event listeners when no longer needed.

## Required quality gates

Every meaningful change should include applicable checks for:

- Unit and integration behavior, including IndexedDB where used.
- End-to-end critical user flows.
- Regression cases and invalid/boundary inputs.
- Keyboard accessibility, focus visibility, labels, and contrast.
- Offline behavior and storage migrations.
- Security, dependency advisories, and secret scanning.
- Performance and output size.
- Clean, reproducible builds.

A failed critical test or serious security finding blocks merging. Do not remove or weaken tests to make a change pass. Any justified deferral must document the risk, mitigation, owner approval, and next review date.

## Pull requests

- Keep changes focused and reasonably small.
- Explain behavior changes, privacy/network effects, migrations, and test evidence.
- Update relevant documentation and the changelog.
- Never include secrets, real user data, local databases, or private company integration code.
