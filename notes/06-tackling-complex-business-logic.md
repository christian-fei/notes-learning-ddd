## Domain model pattern

Introduced by Fowler in "Patterns of Enterprise Application Architecture"

The aggregates, value objects, domain events and services are the building blocks

Intended to be used when dealing with complex business logic, e.g. state transitions, business rules and invariants

> a domain model is an object of the domain that integrates both behaviour and data

The model should be unaware of technological/infrastructural concerns, and follow the ubiquitous language of the bounded context.

**Value objects** are identified by the composition of its values, and should be used for the domain's elements that describe properties of other objects.

**Entities** are the opposite of value objects, since they require an explicit identification field to distinguish different instances, and are expected to change (entities are mutable). Furthermore entities shoul only be part of an aggregate, not as an independent pattern. They are the building blocks of an aggregate.

**Aggregates**

An aggregate is an entity, but much more. An aggregate's goal is to protect data consistency.

An aggregate is a *consistency enforcement boundary*, by validating incoming changes and ensure business rules are respected.

Only the aggregate's business logic is allowed to alter the aggregate's state -> Commands.

Adopting this convention ensures that all business logic of the aggregate is implemented in only the aggregate itself.

An aggregate also acts as a *transaction boundary*, since the state can only be modified by the business logic implemented in the aggregate.

Changes should be committed in a transaction, atomically.

Aggregates get the name because the "aggregate" entities and value objects belonging to the same transaction boundary.

Rule of thumb: keep the aggregate as small as possible, requiring only data that is required to be strongly consistent. All other data can be moved outside the consistency boundary of the aggregate(s).

In a aggregate boundary, only one aggregate is the *aggregate root*: the public interface of the aggregate on which you can dispatch commands.

An aggregate can be modified through commands using the public interface, but also with *domain events* coming from the outer world.

A *domain event* describes something that happened in the domain, thus formulated in the past, providing all information related to the event.

An aggregate dispatches domain events, and other aggregates and systems can subscribe to those events.

Aggregates should use the domain language of its bounded context.

**Domain services**

When you encounter business logic that doesn't belong to any aggregate, or is relevant to multiple aggregates, a domain service comes into play.

It's a stateless objects that implements the business logic needed, to orchestrate calls to other system components and perform some calculation.

**Managing complexity**


