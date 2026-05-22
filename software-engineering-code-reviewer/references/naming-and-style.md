# Naming and Style

Code should look native to the language being used, not translated from another language.

## Language conventions

- Java, C#, Kotlin, and TypeScript classes: `PascalCase`
- Java, C#, Kotlin, and TypeScript methods and variables: `camelCase`
- Python functions and variables: `snake_case`
- Constants: follow the language idiom, often `UPPER_SNAKE_CASE`
- Modules and packages: follow the language idiom
- Booleans: use predicate names such as `isValid`, `hasPermission`, `canExecute`, `shouldRetry`, `is_active`, or the local language equivalent

Adjust these conventions when the target language or codebase has a stronger established idiom.

## Domain intent

Names should express domain intent, not implementation trivia. Prefer names that reveal what the concept means in the problem space.

Weak:

- `data`
- `info`
- `temp`
- `thing`
- `doStuff`
- `handle`
- `manager`
- `helper`
- `utils`

Use those names only when they are precise in context. For example, `TemperatureReading` is meaningful; `temp` as a vague temporary value is usually not.

## Function and method names

Use verbs or verb phrases for behavior. The name should tell the reader what outcome or command is being performed.

Prefer:

- `calculateInvoiceTotal`
- `authorizePayment`
- `parseCustomerImportRow`
- `shouldRetry`

Avoid names that hide multiple responsibilities, such as `process`, `handle`, or `run`, unless the surrounding context makes the meaning specific.

## Type and module names

Use nouns or noun phrases for concepts, roles, or boundaries.

Prefer names that identify ownership:

- `PaymentAuthorization`
- `InvoiceRepository`
- `CustomerImportParser`
- `RetryPolicy`

Avoid broad names such as `Common`, `Base`, `Manager`, or `Helper` unless the role is precise and accepted in the codebase.

## Comments

Comments should explain why, not repeat what the code already says.

Good comments clarify:

- Non-obvious business rules
- Trade-offs
- External constraints
- Security or performance reasons
- Workarounds with context

Remove comments that merely narrate obvious implementation steps.

## Style consistency

Follow the surrounding codebase unless it is clearly harmful. If improving style, keep formatting and naming changes focused enough to review.

Prefer idiomatic language constructs for errors, optional values, collections, resource management, asynchronous work, and tests.
