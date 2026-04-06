# Contract Precedence

## Rule

The files in `/docs/contracts/` are the single source of truth.

ARCHITECTURE.md is only a summary and must never override contract definitions.

If there is any conflict:
→ contracts take priority

---

## Cross-System Priority

When evaluating behavior, the following order applies:

1. Tenant context must be valid
2. User must have membership
3. Permission must allow action
4. Scope must allow access
5. Entitlement must allow feature
6. Module must be enabled
7. Config rules must allow behavior

If any step fails:
→ action is denied

---

## Ownership

- Contracts define rules
- Modules implement behavior
- No module may override contract rules