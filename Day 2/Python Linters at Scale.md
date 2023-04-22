# Python Linters at Scale

Some tools
- Black
- isort
- flake8 - code styel, syntax error, and bugs
- mypy


Goal is the dected linter errors ad dev time to iterate fast

Run linters 
- at commit time via git ocmmit hooks
- at dev time via IDE plugins
- as part of Continuous Intergration runs

presenter has 30,000 python files and some linters are slow

For speeding up:
- only run on updated code
- run in parallel
- resuse prior results
- faster implementation

So they use pre-commit which runs on the comitted files (as opposed to all the files)

Ruff is a faster linter implemented with Rust

To understand the developer experience they collected metrics from CI and local runs. Some of the things they are measuring is how much time the linters take to run

They created a PR bot that checks if a PR is too far behind and reminds the dev to rebase so they don't end up with merge conflicts.

Automatically fix flake8 and mypy errors to save developers time - the dev can review and the click to apply the change

