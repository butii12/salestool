# Tenant Isolation Contract

## Goal
Ensure strict separation between organizations in all system layers.

## Rules
- Every tenant-owned record must include `organization_id`
- No request may access tenant data without resolved tenant context
- No cross-tenant queries are allowed in application services
- Tenant context must be enforced in:
  - API layer
  - service layer
  - background jobs
  - reporting layer
- Shared/system-level records must be explicitly marked as global

## Tenant context sources
- authenticated user membership
- explicit tenant header or token claim
- system tasks with explicit tenant assignment

## Async / background jobs
- every job must carry tenant context explicitly
- no background task may run without tenant binding
- cross-tenant batch processing must be system-scoped and explicit

## Reporting rules
- organization-scoped reports only see one tenant
- cross-tenant analytics require explicit superadmin/system scope

## No-bypass rule
No repository/service method may return tenant-owned data without tenant filtering.