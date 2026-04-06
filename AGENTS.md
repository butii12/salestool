# AGENTS.md

## Project
SalesTool is a multi-tenant SaaS platform for call centers and multi-department service organizations.

## Current mode
We are in planning-first mode.
Do not jump into implementation unless the current sprint explicitly allows it.

## Product goals
- One codebase for many companies
- Strict tenant isolation
- Dynamic configuration instead of hardcoded business logic
- Extendable module-based architecture
- Enterprise-ready path with SSO, feature flags, and configurable KPI engines

## Core architecture rules
- Never hardcode KPI definitions, KPI rules, widget behavior, upload behavior, department logic, or per-customer logic
- Always design for:
  - organization scope
  - department scope
  - role/permission scope
- Prefer database/config-driven behavior
- Support future:
  - plans
  - subscriptions
  - feature flags
  - modules
  - SSO
  - auditability

## Working rules
- Read `/docs/PRODUCT_MASTER.md`, `/docs/ROADMAP.md`, and `/docs/CURRENT_SPRINT.md` before doing anything
- Only work on the currently approved scope
- Plan first for non-trivial changes
- Explain architecture tradeoffs before major implementation
- Keep naming explicit and consistent

## Development chain
DB → Model → Migration → Service → API → UI → Audit

## Important systems
- Foundation & Infrastructure
- Multi-Tenant Core
- Organization & Settings
- Departments System
- Auth & Roles
- Plans & Subscriptions
- Feature Flags System
- Module System
- Event System
- KPI Engine
- Data Sources & Uploads
- Processing Layer
- Dashboard System
- Widget System
- Reporting & Exports
- Gamification
- Notifications
- Integrations / API
- SSO & Identity Providers
- Audit Logs
- Configuration Engine

## Non-goals
- No customer-defined executable code
- No hardcoded customer branches
- No shortcut implementation that blocks configurability later