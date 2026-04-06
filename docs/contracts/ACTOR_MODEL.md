# Actor Model

## Actor Types

### 1. User Actor
- authenticated human user
- belongs to organization
- has roles and permissions

---

### 2. System Actor
- internal system process
- no human identity
- full system-level access

---

### 3. Background Job Actor
- async tasks (queue, cron)
- must always include tenant context
- must respect module + config rules

---

### 4. Integration Actor
- external API clients
- uses API keys or OAuth
- limited by scope and permissions

---

### 5. Superadmin Actor
- platform-level access
- can access multiple tenants
- must be explicitly flagged
- all actions must be audited

---

## Rules

- every action must have an actor
- every actor must have a scope
- no anonymous actions allowed
- audit logs must include actor type

---

## Important

Actors must follow:
tenant → permission → scope → entitlement → module → config