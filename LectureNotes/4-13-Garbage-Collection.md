# Garbage collection

Three types of GC that we're going to discuss:

- Refcounting
- Mark and sweep
- Stop and copy

## Mark and sweep

- Memory looks like a list of blocks, each of which is either in use or not in use
- If segment of memory is accessible from variables on stack, is reachable
- If segment of memory not reachable, mark it
- At the end, sweep (free) anything that's marked

Advantages:

- Works with cycles
- No count values like refcounting

Disadvantages:

- Time complexity rises
- Like refcounting, does not help with fragmentation
- Have to stop the world

### Stop and copy

- Heap is split in two partitions (one live, one dead)
- Always `malloc` in live partition
- Go through the stack and everything that it refers to, copy over to the other partition

Advantages:

- Limits fragmentation because you can copy it sequentially
- Deals with cycles
- No need for counter like refcounting

Disadvantages:

- Have to stop the world
- Have to use twice the memory
