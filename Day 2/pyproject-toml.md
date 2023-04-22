# pyproject.toml, packaging, and you

TOML is basically JSON + date + differentiation between float and integer

key/value pairs become a dictionary

Not just for configuring build syste4, but also holds build-system agnostic tools and things like black

if python -m build doesn't work - try the src/ structure

empty setup.cfg no longer needed

using pyproject.toml future-proof's teh build so that you can change to poetry or hatchery or whatever and python -m build should just continue to work

