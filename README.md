# Objective-C Memory Leak: Unbalanced Retain/Release
This repository demonstrates a common Objective-C memory leak scenario caused by improper usage of retain and release methods for manual memory management. The `MemoryLeakBug.m` file contains code that exhibits this issue, while `MemoryLeakSolution.m` provides a corrected version.

**Problem:**
The original code fails to properly balance retain and release calls, leading to an object's retain count remaining greater than zero after it is no longer needed. This results in a memory leak.

**Solution:**
The solution corrects the imbalance by ensuring that each `retain` call is matched with a corresponding `release` call when the object is no longer required.  Proper use of `autorelease` is also demonstrated for cleaner memory management. 

**How to reproduce:**
1. Compile and run `MemoryLeakBug.m`.
2. Monitor memory usage using Activity Monitor (macOS) or similar tools.  Observe the increasing memory consumption.
3. Compile and run `MemoryLeakSolution.m`. Observe the improved memory behavior.