learn about various patterns for integrating and defining relationsships between bounded contexts.

## Cooperation patterns

### Partnership

One team can notify about the requested changes in an API.

The second team will coordinate and communicate about the progress.

Cooperation between both side with high level of commitment.

### Shared kernel

Two bounded contexts could have a shared piece of integration, that both bounded contexts can adapt and modify.

Changes made to the shared part, trigger integration tests in all affected part of the codebase.

Shared kernel is at first sight counterintuitive, since it goes against the "rule" of one team works on a bounded context. 

A shared kernel must be justified, e.g. geographical constraints of the team, gradual modernization of a legacy system.



## Customer - Supplier

The Supplier "provides" a service for its customers. Service provider is upstream, customer/consumer is downstream.

-> Conformist, Anticorruption layer, open-host service patterns

### Conformist

Where a upstream team has a great decisional power and is a dependence on the downstream service.

The downstream conforms to the upstream bounded context's model.

The downstream team gives up some autonomy.

### Anticorruption Layer

When the downstream bounded context is not willing to conform to the upstream API.

Translates the upstream bounded context's model into a model tailored to its own needs via an anticorruption layer.

not ideal when

- downstream bounded context contains a subdomain
- inefficient or inconvenient upstream model for the customer's needs
- frequent supplier contract changes

### Open-Host Service

Practically the opposite of the Anticorruption layer, applied to the upstream side.

Protects the consumer with a stable API, providing the best service possible.

The upstream creates an integration-oriented language, a public protocol called the *published* language.

The supplier implements a translation of its internal model.

Gives flexibility to evolve implementation without affecting downstream.


## Separate ways

No collaboration at all between bounded contexts.

### Communication

Difficult communication (or none at all) can bring to no collaboration, by duplicating functionality in multiple bounded contexts.

### Generic subdomains

When it's objective worth duplicating functionality, e.g. a logging framework

### Model differences

When the models are so different it's not worth implementing an ACL, collaborating in any way



## Context Map

The context map represent the various integration patterns between bounded contexts.

It brings the following advantages

- high-level design, overview of the system's components and models
- communication patterns, e.g. acl, separate ways
- organizational issues, highlights issues between contexts

https://contextmapper.org


## Recap

Partnership: Bounded contexts are integrated in an ad-hoce manner

Shared Kernel: integrated sharing a limited overlapping model that belongs to all bounded contexts

Conformist: consumer conforms to the provider's model

Anticorruption layer: consumer translater the provider's model

Open-host service: provider implements a published language, a model optimized for its consumers' needs

Separate ways: when it's less expensive to duplicate than to collaborate and integrate

A context map shows the integrations between bounded contexts, gives insights about highlevel design, communication patterns and organizational issues.

