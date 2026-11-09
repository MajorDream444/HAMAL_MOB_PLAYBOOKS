# Commerce release checks

Apply before releasing payment or fulfillment flows, especially where a single item, limited stock, seat, or exclusive license can be claimed. For HAMAL Music Engine, first record which offers, if any, are exclusive or quantity-limited, who owns that decision, and which system owns availability. Review checkout separately from intake-only releases.

| Check | What engineering must demonstrate in staging |
| --- | --- |
| Simultaneous buyers | Start two independent checkouts against one available unit. A single authoritative transaction or equivalent atomic operation grants the reservation or claim. Enforce the inventory invariant in storage. Exactly one order can become fulfilled for the unit. The other sees a clear outcome and no unintended charge. |
| Retries and duplicate events | Replay an identical checkout request, simulate a provider timeout after accepting the request, and deliver duplicate and out-of-order events. Use durable operation identifiers and stable provider idempotency keys where supported. Verify webhook signatures, persist receipt/processing state, and guard payment and fulfillment transitions so one business action takes effect once. |
| Expiry and late payment | Race reservation expiry or cancellation against payment success and a new buyer. Correlate payment to the original reservation and make the final transition conditional on ownership. If a stale payment succeeds, prevent fulfillment and follow the approved void, refund, or escalation procedure. Record and reconcile the exception. |
| Recovery and reconciliation | Interrupt processing after a payment or state change, then restart. Reconcile the order, inventory or entitlement, provider payment, and fulfillment. Demonstrate that pending work can be retried safely and unresolved differences are visible to an operator. |
| Audit trail | Reconstruct both checkout attempts and each committed transition from durable records. For state changes, persist the audit record with the state change or use a transactional outbox. Capture UTC time, actor or service, action, before/after state, outcome, reason, and correlated item, reservation, order, and provider IDs as applicable. Restrict access and changes, define retention, and exclude secrets and raw card details. |

Attach the candidate version, test run evidence, unresolved exceptions, and named release decision to the workload receipt. Record any operator override as a separate event with actor and reason. The workload owner defines the refund, cancellation, and fulfillment policies before the flow can pass release review.

Implementation references for teams using these services:

- [PostgreSQL transaction isolation](https://www.postgresql.org/docs/16/transaction-iso.html)
- [Stripe webhook delivery and verification](https://docs.stripe.com/webhooks)
- [Stripe idempotent requests](https://docs.stripe.com/api/idempotent_requests)
