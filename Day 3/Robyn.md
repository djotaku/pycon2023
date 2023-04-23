# Robyn: An async Python web framework with a Rust runtime

https://www.github.com/sansyrox/robyn

For speaker, his priorities when comparing frameworks

- performance
- ease of use
- scalability
- build-in features
- extensibility
- hacker friendliness
- community
- end-to-end app creation timeline

## Performance

Can serve over a million requests per second

Part of what makes it faster is that it has a multi-threaded rust runtime

Python code is converted to rust objects at app start time

Also supports multi-processes

## Ease of Use

Robyn API desgin is very similar to flask API (example shown was a drop-in replacement, but it was a toy app)

Robyn doesn't need ASGI/WSGI - it has one built-in. This helps it to go faster than other web frameworks

## Scalability

You can organize code into Views (functional views) or Routers (like in FastAPI)

## Built-In Features

- sync
- Async supported
- directory serving
- file serving
- middleware
- application events

## Extensibility

pip install robyn[extension]

- support jinja templates
- also has a template interface so you can override it
- GraphQL support

## Hacker Friendliness

- const requests - which are optimized
- web sockets - can be used as replacement for queue
- no need to choose a server since the *SGIs are not needed

## End-to-End App Creation Timeline

one command creation (missed the page, see the notes)

python -m robyn --docs - allows you to see docs in the CLI

## Community 

will move to github.com/sparckles/robyn




