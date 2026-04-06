# Configuration Contract

## Goal
Define how configuration works across all scopes.

## Configuration levels
1. Global defaults
2. Plan level
3. Organization level
4. Department level

## Precedence
Global → Plan → Organization → Department

## Rules
- Configuration must be schema-based
- Configuration must be validated before activation
- Configuration must be versionable
- Configuration must be auditable
- Modules may contribute config only within their own namespace

## Ownership
- global config: platform owner
- plan config: SaaS/business layer
- organization config: tenant admin
- department config: delegated department admin (if allowed)

## Override semantics
- scalar values: replace
- objects: merge by key
- lists: explicit strategy per config type
- invalid config must be rejected

## Safety
- no arbitrary executable code in config
- no unsafe customer-defined logic
- config changes must generate audit logs