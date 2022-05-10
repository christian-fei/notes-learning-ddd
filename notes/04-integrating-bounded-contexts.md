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

