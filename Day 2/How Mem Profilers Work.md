# How Memory Profilers Work

It can ask for memory, but it's not filled utnil you're writing to it. 

Where is my memory?
- RAM
- swap (hard drive)
- RAM + swap
- Nowhere - we requested, but haven't started using it

When you ask kernel for memory, it actually gives you a virtual memory map (not an actual address in RAM)

