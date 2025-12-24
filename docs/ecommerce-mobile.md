Case — E-Commerce Mobile Application

System Type
Mobile-first e-commerce platform with high checkout concurrency and payment sensitivity.

Constraints

Mobile clients only (no desktop fallback)

High transaction volume during campaigns

Zero tolerance for duplicate charges

Payment confirmation must be server-authoritative

Architecture

API-driven backend

Stateless application layer

Mobile app as primary client

Server-controlled order lifecycle

Technology Stack

Mobile: Flutter

Backend: Node.js

Database: PostgreSQL

Payments: Stripe

Infra: Cloud load balancer + auto-scaling

Key Engineering Decisions

Enforced idempotent payment requests at API level

Moved order finalization logic fully server-side

Treated payment webhooks as source of truth

Rejected client-side payment confirmation

Engineering Issues Encountered

Duplicate payment attempts under poor network conditions

Race conditions between client callbacks and payment webhooks

Inconsistent order states during retries

Resolution

Idempotency keys tied to checkout session

Single authoritative order state machine on backend

Webhook-driven reconciliation for payment status

Retry-safe checkout flow

Measured Impact

Payment failure rate reduced significantly

Zero duplicate charges after deployment

Stable checkout behavior during traffic spikes
