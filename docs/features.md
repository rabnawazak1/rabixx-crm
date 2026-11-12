# Features

RabixxCRM is organised feature-by-feature. Each feature below maps to a module in the app.

## 🔑 Authentication

- Sign in with ERP credentials against the `api/v1` endpoint
- Session tokens issued by **Laravel Sanctum**
- Tokens stored with **flutter_secure_storage** (never in plain preferences)
- Route guarding so protected screens redirect to login when signed out

## 📊 Dashboard

- A landing view summarising the agent's day
- Visual breakdowns powered by **fl_chart**
- Quick jump-off points into leads and follow-ups

## 📇 Leads

- Browse and search the assigned lead list
- Open a lead to see its detail and history
- Field-friendly quick actions (for example, tap to call via `url_launcher`)

## ⏰ Follow-ups

- A focused list of what needs a callback or next touch
- Backed by the ERP's **activity** model (follow-ups are activities of type `follow_up`), so mobile and desktop stay in sync
- Dedicated widgets for a fast, scannable layout

## 👤 Profile

- The signed-in agent's details
- Sign-out and account actions

## 🔔 Notifications

- **Firebase Cloud Messaging** for server-pushed alerts
- **flutter_local_notifications** for on-device reminders
- Device tokens registered with the ERP so the backend can target an agent

## 🧭 Cross-cutting

- **Connectivity awareness** — the app reacts to network changes in the field
- **Material 3** theming with custom fonts (Google Fonts)
- Centralised error handling with a typed result model
