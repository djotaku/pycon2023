# How Pydantic V2 leverages Rust's Superpowers

V2 is a bluesky sort of release - "waht woudl it look like if we started from scratch?"

Priorities:
- Performance
- Strict Mode - a mode where data isn't coerced
- Composability - "you don't always want a model"
- Maintainability - of Pydantic itself

Using Rust allows for multithreading - since no GIL

Validation leads to a complex tree - this runs better/faster in Rust

22x faster in V2

Generics are improved in V2 - biggest thing in V2 is that recursive generics now work



