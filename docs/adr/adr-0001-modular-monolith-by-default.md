# ADR-0001: Default to Modular Monolith

## Status
Accepted

## Context
Team projects are small-to-medium with 1-5 developers and uncertain product scope. Premature microservices would add operational burden (deployment, observability, distributed transactions) without benefit at current scale.

## Decision
New services default to a modular monolith: one deployable unit with strictly enforced internal module boundaries. Distribution is introduced only when justified by scale, team boundaries, deployment independence, fault isolation, or regulatory need.

## Alternatives Considered
- Microservices from day one: rejected - operational cost unjustified at current scale.
- Single-layer app with no module boundaries: rejected - removes escape hatches.

## Consequences
### Positive
Fast iteration, simple deploys, easy local testing, refactor-friendly.
### Negative
Requires discipline to keep module boundaries honest.
### Risks
Boundaries eroding into a big ball of mud; mitigated by architecture-review skill and CI checks.

## Security Considerations
One trust boundary at the app edge initially; internal modules do not hold separate credentials.

## Performance Considerations
Single-process latency is fine at current scale; measure before splitting.

## Operational Considerations
One deployment pipeline; observability at module level via structured logs.

## Migration
N/A - this is the starting posture for new projects.

## Validation
Quarterly architecture-review runs check that module boundaries remain explicit.
