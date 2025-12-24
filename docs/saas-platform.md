Case — SaaS Platform Development

System Type
Subscription-based SaaS platform with controlled growth requirements.

Constraints

Predictable scaling over rapid complexity

Limited engineering team

Strong separation between billing and core logic

Zero downtime releases

Architecture

Modular monolith

Clear domain boundaries

Shared database with strict access layers

Technology Stack

Backend: Node.js

Frontend: React

Database: PostgreSQL

Auth: JWT + refresh tokens

Billing: Stripe Subscriptions

Key Engineering Decisions

Rejected microservices to avoid operational overhead

Isolated billing logic from core business logic

Implemented feature flags for controlled rollouts

Chose schema-based migrations over ad-hoc changes

Engineering Issues Encountered

Subscription state drift after failed payments

Inconsistent access control during plan changes

Deployment risk during schema updates

Resolution

Centralized subscription state handling

Explicit entitlement checks at API level

Backward-compatible schema migrations

Blue-green deployment strategy

Measured Impact

Predictable scaling without architectural rewrites

Reduced production incidents

Controlled release process with minimal risk
