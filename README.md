# Fully Associative (FA) + LRU Cache Simulator
This is a Python application that simulates a fully associative cache using the Least Recently Used (LRU) replacement policy. It demonstrates how cache blocks are loaded, evicted, and accessed under different memory‐access patterns. The simulator also provides a step‐by‐step trace log as well as overall statistics (cache hits, misses, hit rate, etc.) for analysis.

# Getting Started
# Prerequisites 
To run this program, you will need Python 3.7 or later installed on your system.
You can verify your Python version by running in command prompt:
python --version

# Installation
1. Clone/Download this repository
2. Open a command prompt in the project directory

# Running the Program
from your project folder, run python 
cache_sim_fa_lru.py

# Usage
1. Enter hte number of cache blocks when prompted.
2. Choose one of the three test cases:
- Sequential Access: Accesses 0 to 2n - 1 (where n = number of cache blocks) in order, repeated four times.
- Random Access: Accesses 4n memory blocks in random order.
- Mid-Repeat Blocks: Demonstrates accessing 0..n-1, repeating that range, then n..2n-1, with repetitions to test reuse and eviction patterns.
3. After you select a test case, the program will:
- Perform the sequence of memory acccesses.
- Print a Final Cache Snapshot to show which blocks remain in the cache
- Save a detailed memory tracelog to a text file (e.g., sequential_access_log.txt, etc.)

 # Output
 1. Cache Memory Snapshot: Lists the blocks currently in cache after the simulation completes.
 2. Access Log File: Logs each memory access, indicating “HIT” or “MISS,” plus any evictions performed.
 3. Statistics
- Total Memory Accesses
- Cache Hits/Misses
- Cache Hit Rate/Miss Rate

# Credits
- @ryanvillanueva0930
- @IanRein
- @LGGMaloles
- @antonluisvale@gmail.com
