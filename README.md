# Functional and Reactive Domain Modeling

by Debasish Ghosh

## Functional Domain Modeling

### Definitions

- Domain
  - The area of interest in the business.
  - A blueprint of the relationships between the various entities of the problem domain and sketches out other important details (objects, behaviours, language, context...).
  - _Example_: personal banking business.
- Bounded context
  - One complete functionality within your system.
  - _Example_: tax reports, deposit management...
- Entities
  - Items with an identity that has to be managed in the course of its entire lifetime within the system.
  - Semantically mutable.
  - _Example_: account.
- Value objects
  - Items identified entirely based on the value it contains.
  - Semantically immutable.
  - _Example_: address.
- Services
  - Encapsulate behavior involving value objects and entities.
  - _Example_: account service.
- Aggregates
  - Group of related objects defining a consistency boundary.
  - Can consist of one or more entities and value objects.
  - One of the entities is the aggregate root. It...
    - Ensures consistency boundary of business rules and transactions within the aggregate.
    - Prevents the implementation of the aggregate from leaking out to its clients acting as a
façade for all the operations that the aggregate supports.
  - _Example_: account, containing bank, address, dates...
- Repositories
  - Interface to persist entites.
  - _Example_: `AccountRepository`, implemented by `AccountRepositoryPostgresql` and `AccountRepositoryInMemory`.
