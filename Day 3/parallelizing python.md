# Getting Around the GIL: Parallelizing Python for Better Performance

If you have a python app that needs lots of ram, you'd probably end up with an AWS VM that has 48 cores, but Python can only use one of them. It could cost you $2190/yr instead of $45/year

GIL is about reference counting

Difference between concurrency and paralllalism

Concurrency is about dealing with lots of thigns at once

Parallelism is about doing lots of things at once

2 main ways around the GIL:

- Partially Parallel 
    - threading
    - multiprocessing
    - subprocess
    - asyncio
    - dask
    - pyspark
    - modin
    - ray

- Truly Parallel
    - bodo
    - mpi4py
    - bodo.ai

Some of the ways that python is sped is up is to use a JIT compiler

