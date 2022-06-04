## Domain model pattern

Introduced by Fowler in "Patterns of Enterprise Application Architecture"

The aggregates, value objects, domain events and services are the building blocks

Intended to be used when dealing with complex business logic, e.g. state transitions, business rules and invariants

> a domain model is an object of the domain that integrates both behaviour and data

The model should be unaware of technological/infrastructural concerns, and follow the ubiquitous language of the bounded context.

**Value objects** are identified by the composition of its values, and should be used for the domain's elements that describe properties of other objects.

**Entities** are the opposite of value objects, since they require an explicit identification field to distinguish different instances, and are expected to change (entities are mutable)

**Aggregates**

An aggregate is an entity, but much more. An aggregate's goal is to protect data consistency.

An aggregate is a consistency enforcement boundary, by validating incoming changes and ensure business rules are respected.

Only the aggregate's business logic is allowed to alter the aggregate's state.

