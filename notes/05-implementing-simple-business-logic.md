Two patterns suited to model and implement simple business logic: Transaction Script and Active Record

## Transaction Script

> Organizes business logic by procedure where each procedura handles a single request from the presentation - Martin Fowler

An objects public interface can be seen as a collection of business transactions that consumers can execute.

The public operations are used to encapsulate boundaries.

The implementation should be consistent, rolling back changes where failures happen, transactions can be very helpful to guarantee consistency.

> This pattern organizes the system's operations as simple procedural scripts. Each operation is transactional. Best in supporting subdomains, with ETL like business logic

### When to use Transaction Script

Ideal for supporting subdomains (simple domain logic). Should never be used for core subdomains because of its complexity.

Can be used as an adapter for integration with external systems, or as part of an Anti-corruption layer.


## Active Record

> An object that wraps a row in a database table or view, encapsulates the database access, and adds domain logic on that data - Martin Fowler

Ideal for simple business logic is used, where the business may operate on more complex data structures.

Use of dedicated objects to represent complicated data structures, aka Active Records.

The use of "active" comes from the fact that each data structure implements data access logic.

Best applied to supporting subdomains, due to their limited complexity and business logic.

Active record addresses the complexity of mapping complicated data structures to a database's schema.

> Simple business logic, complicated data structures. An active record is a data structure that provides simple CRUD data access methods.
