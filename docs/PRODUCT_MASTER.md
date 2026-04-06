# SalesTool Product Master

## Vision
SalesTool is a configurable multi-tenant SaaS platform for call centers and service organizations.
It supports multiple organizations, multiple departments per organization, dynamic KPI systems, configurable dashboards, configurable uploads/data sources, feature-based subscriptions, and future enterprise identity support.

## Core principles
- Multi-tenant by design
- No hardcoded KPI logic
- No hardcoded widgets
- No hardcoded upload logic
- No hardcoded department structure
- Configuration-driven architecture
- Modular system design
- Enterprise-ready roadmap

## Organizational structure
- Organization
- Department
- Optional sub-department / team
- User
- Role
- Permission
- Membership

## Major systems
1. Foundation & Infrastructure
2. Multi-Tenant Core
3. Organization & Settings
4. Departments System
5. Auth & Roles
6. Plans & Subscriptions
7. Feature Flags System
8. Module System
9. Event System
10. KPI Engine
11. Data Sources & Uploads
12. Processing Layer
13. Dashboard System
14. Widget System
15. Reporting & Exports
16. Gamification
17. Notifications
18. Integrations / API
19. SSO & Identity Providers
20. Audit Logs
21. Configuration Engine

## What must stay dynamic
- KPI definitions
- KPI targets
- KPI rules
- KPI weights
- dashboard widgets
- dashboard layouts
- upload mappings
- data sources
- module activation
- feature availability
- organization branding
- department settings

## SSO requirements
The system must support future:
- SAML
- OAuth
- OpenID Connect
- external identity mapping
- domain-based login routing

## Product shape
One platform for many companies, with per-tenant branding, department structure, features, KPI logic, and dashboard behavior.