# SalesTool Architecture (Cross-Cutting)

## 1. Tenant Isolation Model

- Every record must belong to an organization_id
- No data access without tenant context
- Tenant context must be resolved on every request
- No cross-tenant queries allowed

---

## 2. Configuration Model

Configuration exists on multiple levels:

1. Global defaults
2. Plan level
3. Organization level
4. Department level

Priority:

Global → Plan → Organization → Department

Configuration must:
- be JSON-based
- be validated
- support overrides
- support versioning (future)

---

## 3. Permission Model

Scopes:

- organization
- department
- own

Rules:
- Every request must be validated against role + scope
- No direct DB access without permission check

---

## 4. Feature Resolution Model

Final feature availability is determined by:

Plan → Feature Flags → Modules → Organization Overrides

Example:

Enterprise Plan
→ Feature enabled
→ Module enabled
→ Organization allows

---

## 5. Module System Rules

- Modules must be independent
- Modules may depend on other modules
- Modules must be enable/disable capable
- Modules must not hardcode logic

---

## 6. Event System

- All business actions produce events
- Events are stored and processed
- Systems like KPI, Gamification, Notifications depend on events

---

## 7. KPI Engine Rules

- KPIs must be fully dynamic
- No hardcoded KPI logic
- KPI = definition + rules + weights + events

---

## 8. Dashboard & Widget Rules

- Widgets must be configuration-driven
- Dashboards must support per-role and per-department views
- No hardcoded dashboards

---

## 9. Data Flow

Data flow must follow:

Input (uploads/API/manual)
→ Validation
→ Event creation
→ Processing
→ KPI update
→ Dashboard

---

## 10. Audit Rules

- Every important action must be logged
- Actor + entity + timestamp required
- Must support filtering and tracing

---

## 11. SSO & Identity

- System must support:
  - SAML
  - OAuth
  - OpenID
- Users may have external identities
- Login method may vary per organization

---

## 12. System Rule (IMPORTANT)

No business logic should be hardcoded.

Everything must be:
- configurable
- extendable
- tenant-aware