# Authorization and Entitlement Contract

## Goal
Separate identity, permissions, scope, and feature access clearly.

## Concepts
- Authentication = who the user is
- Authorization = what the user may do
- Scope = where the user may do it
- Entitlement = whether the tenant plan/module allows it

## Scope levels
- organization
- department
- own

## Rules
- every protected action requires:
  1. authenticated identity
  2. active tenant membership
  3. permission check
  4. scope check
  5. entitlement check (plan/feature/module)

## Permissions
Permissions must be explicit and named, e.g.:
- users.read
- users.write
- reports.view
- kpi.manage

## Tenant membership
No user may act in a tenant without membership.

## Module/feature relation
Even if a role has permission, the action must fail if:
- module is disabled
- feature is disabled
- tenant plan does not allow it

## Audit-sensitive actions
The following must always be audited:
- auth events
- role/permission changes
- config changes
- KPI/rule changes
- module activation/deactivation