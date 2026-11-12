# Architecture

RabixxCRM uses a **feature-first clean architecture**. Each feature is a vertical slice with its own data, domain, and presentation layers, so features stay independent and testable.

## Project layout

```
lib/
├── core/                  # app-wide building blocks
│   ├── config/            # dart-define based configuration
│   ├── error/             # typed Result<T> / failure model
│   ├── network/           # Dio client + interceptors (auth, error, logging)
│   ├── notifications/     # FCM + local notification setup
│   ├── routing/           # GoRouter (shell + branches)
│   ├── storage/           # secure storage keys
│   ├── theme/             # Material 3 theme & design constants
│   └── utils/
├── features/
│   ├── auth/
│   ├── dashboard/
│   ├── leads/
│   ├── follow_ups/
│   └── profile/
└── shared/
    └── widgets/           # reusable UI (e.g. the navigation shell)
```

## Layers inside a feature

Each feature follows the same three-layer shape:

```
features/<feature>/
├── data/
│   ├── datasources/       # remote (API) and local sources
│   ├── models/            # DTOs (Freezed + json_serializable)
│   └── repositories/      # repository implementations
├── domain/
│   ├── entities/          # pure business entities
│   └── repositories/      # repository interfaces (contracts)
└── presentation/
    ├── providers/         # Riverpod state (AsyncNotifier, etc.)
    ├── screens/           # screens / pages
    └── widgets/           # feature-specific widgets
```

**Dependency direction:** `presentation → domain ← data`. The domain layer defines the contracts; the data layer implements them; the presentation layer depends only on the domain. This keeps UI and networking swappable without touching business logic.

## State management

- **Riverpod** for state and dependency injection
- Code-generated providers via `riverpod_generator`
- Async UI states (loading / data / error) modelled with `AsyncNotifier`

## Navigation

- **GoRouter** with a `StatefulShellRoute` — a bottom navigation shell with independent branches for the main sections
- A redirect guard sends unauthenticated users to the login screen

## Networking

- **Dio** HTTP client with interceptors for:
  - attaching the Sanctum bearer token,
  - normalising errors into the app's `Result`/failure model,
  - request/response logging in debug.
- Talks to the Rabixx ERP `api/v1` endpoints.

## Models & immutability

- **Freezed** for immutable data classes and unions
- **json_serializable** for JSON (de)serialisation of API payloads
