<h1 align="center">RabixxCRM</h1>

<p align="center">
  An Android field-agent app for sales teams — manage leads and follow-ups on the move.<br/>
  The mobile companion to <a href="https://github.com/rabnawazak1/rabixx-erp">Rabixx ERP</a>.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Flutter-02569B?style=flat-square&logo=flutter&logoColor=white" alt="Flutter"/>
  <img src="https://img.shields.io/badge/Dart-3.5-0175C2?style=flat-square&logo=dart&logoColor=white" alt="Dart"/>
  <img src="https://img.shields.io/badge/Riverpod-state-40C4FF?style=flat-square" alt="Riverpod"/>
  <img src="https://img.shields.io/badge/platform-Android-3DDC84?style=flat-square&logo=android&logoColor=white" alt="Android"/>
  <img src="https://img.shields.io/badge/status-in%20active%20development-blue?style=flat-square" alt="Status"/>
</p>

> **About this repository**
> This is a public **showcase** of RabixxCRM — it documents the app's architecture and features.
> The application source code lives in a private repository and is **not** published here.

---

## What is RabixxCRM?

RabixxCRM puts the CRM side of [Rabixx ERP](https://github.com/rabnawazak1/rabixx-erp) in a salesperson's pocket. Agents in the field can review their leads, log activities, and stay on top of follow-ups without opening a laptop. The app talks to the ERP's versioned `api/v1` layer and authenticates with **Laravel Sanctum** tokens.

It's built with a **feature-first clean architecture** so every feature keeps its own data, domain, and presentation layers — the same discipline the ERP applies on the backend.

## Highlights

- 🔑 **Token auth** — sign in against the ERP API, with credentials kept in secure storage
- 📇 **Leads** — browse, search, and work the lead list
- ⏰ **Follow-ups** — never miss a callback (backed by the ERP's activity model)
- 📊 **Dashboard** — a quick read on the day, with charts
- 🔔 **Push notifications** — Firebase Cloud Messaging + local notifications
- 📞 **Field actions** — tap to call and other quick actions
- 🧭 **Connectivity-aware** — adapts to patchy signal in the field
- 🎨 **Material 3** — a clean, modern Android UI

## Explore the docs

| Document | What's inside |
|---|---|
| [**Features**](docs/features.md) | What each part of the app does |
| [**Architecture**](docs/architecture.md) | Clean architecture, state management, and routing |
| [**Tech stack**](docs/tech-stack.md) | Flutter packages and tooling |

## At a glance

| | |
|---|---|
| **Framework** | Flutter (Dart ^3.5) |
| **State / DI** | Riverpod |
| **Routing** | GoRouter |
| **Networking** | Dio → Rabixx ERP `api/v1` (Sanctum) |
| **Push** | Firebase Cloud Messaging |
| **Platform** | Android-first |

---

<p align="center"><sub>Part of the Rabixx platform — see also <a href="https://github.com/rabnawazak1/rabixx-erp">Rabixx ERP</a>.</sub></p>
