# Architecture Principles

Use these principles pragmatically. Do not force a pattern when a simple boundary, function, or type solves the problem.

## Separation of Concerns

Keep different reasons for change apart when mixing them makes code harder to test or change. Common boundaries include domain rules, use-case orchestration, UI, persistence, network, filesystem, framework adapters, and external services.

## Single Responsibility

A unit should have one clear reason to change. Split code when one function, class, or module is responsible for unrelated policies or workflows.

## High Cohesion

Group behavior and data that naturally belong together. Cohesive modules are easier to understand because their operations share a purpose.

## Low Coupling

Reduce unnecessary knowledge between modules. Prefer stable contracts at boundaries where concrete details are volatile or expensive to test.

## Encapsulation

Protect invariants inside the owning type or module. Avoid public mutable state that allows callers to create invalid combinations or bypass business rules.

## Dependency Inversion

Depend on abstractions when it reduces coupling to volatile details such as databases, network clients, clocks, queues, or third-party services. Do not introduce interfaces just to satisfy a rule; introduce them when they clarify ownership, testing, or replacement.

## Tell, Don't Ask

Prefer asking an object or module to perform behavior over extracting its internals and making decisions elsewhere. Use this when it improves encapsulation. Do not hide simple data transformations behind unnecessary methods.

## Information Expert

Place behavior near the data and rules it needs most. The module with the information required to make a decision is often the best owner of that decision.

## Controller

Use a controller or application service to coordinate a use case. It should orchestrate input, authorization, transactions, and calls to domain behavior without becoming a container for all business rules.

## Creator

Let a type create objects it owns, aggregates, or closely uses. Use factories when construction becomes complex, requires validation, or needs to hide infrastructure choices.

## Pure Fabrication

Create a service or helper module when no domain object is a natural owner and the new abstraction improves cohesion or reuse. Avoid vague dumping grounds named `Helper`, `Manager`, or `Utils`.

## Polymorphism

Use polymorphism, strategy, or dispatch when repeated branching represents real behavioral variation by type, provider, state, or rule. Keep simple conditionals when they are clearer and stable.

## Protected Variations

Identify likely points of change and protect the rest of the system from them with stable boundaries. Apply this to payment providers, persistence, external APIs, file formats, feature policies, and framework details when volatility is real.

## DTOs when useful

Use DTOs to cross boundaries between layers, processes, APIs, or persistence models. Avoid using DTOs as mechanical copies everywhere. A DTO is useful when it prevents leaking internal models or clarifies a boundary.

## Layered architecture

Layered architecture is useful when the system has meaningful domain rules or multiple delivery and infrastructure mechanisms.

Typical direction:

- UI or transport layer handles user or protocol concerns.
- Application layer coordinates use cases.
- Domain layer owns business rules and invariants.
- Infrastructure layer implements persistence, network, filesystem, and external integrations.

Dependencies should generally point inward toward stable policy, with infrastructure depending on domain contracts rather than domain code depending directly on infrastructure details.

## Ports and adapters

Use ports and adapters when business logic should remain independent of external systems. Define ports around use-case needs, not around every method of a third-party client.

Good candidates include payment gateways, notification services, repositories, clocks, random generators, storage, queues, and external APIs.

## Domain logic separated from infrastructure

Keep domain decisions out of controllers, database models, UI components, and API clients when those decisions need to be tested, reused, or protected from framework changes.

Small scripts and simple CRUD applications may not need heavy separation. Choose boundaries based on complexity, change rate, and risk.

## Avoiding pattern abuse

Do not introduce layers, interfaces, factories, strategies, or domain models without a concrete reason. Prefer the simplest design that protects current behavior and likely change points. Remove abstraction when it only renames complexity or makes navigation harder.
