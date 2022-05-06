## Inconsistent models

It can happen that a term has a different meaning depending on the mental model of the domain experts in various departments of the company.

E.g. a "lead" in the marketing department could have a different meaning than in the sales deparment.

A unhealthy approach would be to create a single model that can be applied to both diverging definitions and by both departments. 

Another risky approach would be to prefix a term a definition with the department in which it is used:

"Marketing lead"/"Sales lead", but that has the disadvantage of not being aligned with the ubiquitous language and people won't use the prefix in conversations, since humans can rely on the conversation's context.

In this case the domain-driven design pattern "Bound context pattern" comes in.

## Bounded context

"Divide the ubiquitous language into multiple smaller languages, then assign each one to the explcit context in which it can be applied: its bounded context".

E.g. we could have two bounded contexts like marketing and sales

This helps to tackle inconsistencies in the ubiquitous language by splitting it into bounded contexts.

## Model boundaries

Example maps: maps represent the world, but there are different types of maps used for different purposes. One map could be totally irrelevant and useless when applied to a certain context and use.


