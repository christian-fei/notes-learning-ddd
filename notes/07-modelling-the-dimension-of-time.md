Introducing the "event-source domain model pattern"; key difference is how the aggregate is persisted, persisting each change (through domain events) and become the source of truth for the aggregate's state.

## Event-sourcing

By persisting changes to an aggregate (domain events) instead of it's state (and modify it directly) you can gather important business information and answer questions about your domain.

E.g. the history of a customer, order etc.

Event-sourcing models the dimension of time.

The events tell the story of an aggregate.

Append-only, no modification of past events is allowed.

## Event-sourced domain model

All changes to an aggregate must be expressed as events.

The events stored represent the aggregates state.

Executes domain commands and emits new domain events.

### Advantages

- information about an aggregate's history
- automatic audit log
- extract business insights from your aggregate

### Disadvantages

- more effort to model the aggregate
- architectural complexity
- learning curve
- changes to aggregate become more tedious (event versioning etc.)

#### Notes on deleting data (e.g. GDPR)

See "forgettable payload pattern", where sensitive info is encrypted in the event payload and only accessible through an encryption key. Deleting the associated encryption key, makes the sensitive data inaccessible.

