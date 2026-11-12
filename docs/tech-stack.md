# Tech stack

## Core

| Package | Role |
|---|---|
| **Flutter** (Dart ^3.5) | App framework |
| **flutter_riverpod** / **riverpod_annotation** | State management & dependency injection |
| **go_router** | Declarative routing with a navigation shell |
| **dio** | HTTP client for the Rabixx ERP API |

## Data & models

| Package | Role |
|---|---|
| **freezed_annotation** / **freezed** | Immutable models & unions |
| **json_annotation** / **json_serializable** | JSON (de)serialisation |
| **flutter_secure_storage** | Encrypted storage for auth tokens |
| **connectivity_plus** | Network connectivity awareness |
| **uuid** | Client-side identifiers |

## Notifications

| Package | Role |
|---|---|
| **firebase_core** / **firebase_messaging** | Firebase Cloud Messaging |
| **flutter_local_notifications** | On-device notifications |
| **timezone** | Correct scheduling across time zones |

## UI & utilities

| Package | Role |
|---|---|
| **google_fonts** | Typography |
| **fl_chart** | Dashboard charts |
| **url_launcher** | Tap-to-call and external links |
| **intl** | Dates, numbers, and formatting |
| **cupertino_icons** | Icon set |

## Build & dev tooling

| Package | Role |
|---|---|
| **build_runner** | Code generation runner |
| **riverpod_generator** | Generates Riverpod providers |
| **flutter_lints** | Lint rules |
| **flutter_launcher_icons** | App launcher icons |
| **flutter_native_splash** | Native splash screen |

## How it connects

```
RabixxCRM (Flutter)
      │  Dio + Sanctum bearer token
      ▼
Rabixx ERP  api/v1   ──►  CRM domain (leads, activities, follow-ups)
```

The app is **Android-first** and designed to pair with the ERP backend rather than run standalone.
