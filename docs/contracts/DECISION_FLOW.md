# System Decision Flow

## Protected Action Evaluation

Every action in the system must follow this order:

1. Resolve tenant context
2. Validate user authentication
3. Validate tenant membership
4. Check permission
5. Check scope (organization / department / own)
6. Check entitlement (plan + feature flags)
7. Check module activation
8. Check module dependencies
9. Apply configuration rules
10. Execute action

---

## Failure Rule

If any step fails:
→ stop execution
→ return error

---

## Example

User wants to view KPI dashboard:

1. Tenant resolved
2. User authenticated
3. User belongs to organization
4. Permission: dashboard.view → OK
5. Scope: department → OK
6. Plan allows dashboards → OK
7. Dashboard module enabled → OK
8. Dependencies satisfied → OK
9. Config allows access → OK
10. Data returned

---

## Important

No system may bypass this flow.