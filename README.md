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

from your project folder, run 
python cache_sim_fa_lru.py

# Usage

1. Enter The number of cache blocks when prompted.
2. Choose one of the three test cases:
  - Sequential Access: Accesses 0 to 2n - 1 (where n = number of cache blocks) in order, repeated four times.
  - Random Access: Accesses 4n memory blocks in random order.
  - Mid-Repeat Blocks: Demonstrates accessing 0..n-1, repeating that range, then n..2n-1, with repetitions to test reuse and eviction patterns.
3. After you select a test case, Click Run Simulation the program will:
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

# Analysis of the Three Test Cases

# 1. Sequential Access (Test Case 1)

Pattern:
  - Access memory blocks in order from 0 to 2n-1, repeating the sequence 4 times.
  - Example for n=8: 
  0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14, 15
  (repeats 4 times)

Observations:
  - Cache misses dominate initially as the cache fills up.
  - Once the cache is full, every new block replaces the oldest block (LRU).
  - Since the sequence is long (2n blocks), previously used blocks are evicted before reuse, causing low hit rates.
  - Hit Rate: Low (~0% for small caches)
  - Miss Rate: Very High (~100% initially)

Use Case:
  - This pattern is inefficient for FA + LRU caches when working with datasets larger than the cache size.

# 2. Random Access (Test Case 2)

 Pattern:
   - Access 4n random memory blocks.
   - Example for n=8:
  13, 45, 3, 22, 7, 61, 11, 35, ...

Observations:
  - Hit rate depends on randomness
    - If memory addresses repeat often, LRU retains frequently used blocks → Higher hit rate.
    - If completely random, blocks rarely stay in cache → Lower hit rate.
  - Miss Rate varies significantly:
    - Frequent blocks lead to higher cache reuse (better performance).
    - Completely unique accesses result in a near 100% miss rate
  - Expected Hit Rate: Highly variable (depends on access pattern).
  - Miss Rate: Moderate to High.

Use Case:
  - This pattern simulates real-world workloads, such as random memory accesses in multitasking environments.

# 3. Mid-Repeat Blocks (Test Case 3)

Pattern:
  1. Access blocks 0 to n-1.
  2. Repeat 0 to n-1 again (2nd pass).
  3. Access n to 2n-1.
  4. Repeat the entire sequence 4 times.
  - Example for n=8:
  0,1,2,3,4,5,6,7, 0,1,2,3,4,5,6,7, 8,9,10,11,12,13,14,15 (repeats 4 times)

Observations:
  - Initial phase fills cache (0 to n-1).
  - The repeat in the middle benefits from LRU (blocks 0 to n-1 are reused).
  - New blocks (n to 2n-1) cause evictions → Misses increase.
  - Hit Rate: Moderate (~50% or higher).
  - Miss Rate: Moderate.

Use Case:
  - This pattern represents loop-based access in programs with frequent data reuse (e.g., nested loops in software).

# Credits

  - @ryanvillanueva0930
  - @IanRein
  - @LGGMaloles
  - @antonluisvale@gmail.com
