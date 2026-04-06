# Module Interaction Contract

## Goal
Ensure modules stay independent, replaceable, and safe to evolve.

## Rules
- modules must own their own entities and config
- module boundaries must be explicit
- module dependencies must be declared
- modules must tolerate disabled dependencies safely

## Allowed interaction patterns
- direct service contract for tightly-coupled platform services
- event-driven interaction for business workflows
- no hidden cross-module database coupling

## Dependency rules
- dependencies must be one-way
- no circular dependencies
- disabling a required dependency must block dependent module activation

## Communication
Preferred:
- events for business reactions
- service interfaces for explicit synchronous workflows

## Config ownership
A module may only manage config inside its own namespace.

## Disablement behavior
If a module is disabled:
- its UI must disappear
- its actions must be blocked
- its dependent modules must be re-evaluated
- historical data must remain readable if policy allows

## Audit
Module activation, disablement, and dependency failures must be auditable.