# Kotlin removeIf() Gotcha: Lists vs. Maps

This repository showcases a common pitfall when using the `removeIf` function in Kotlin with Lists and Maps.  The behavior is subtly different and can lead to unexpected results if not understood.

**The Problem:**

`removeIf` modifies the collection directly when used with Lists, but when used with Maps (on the entrySet), it modifies the iterator instead of the map. This can lead to only removing entries from the iterator and not the map itself.

**How to Reproduce:**

1. Clone this repository.
2. Run `bug.kt`.
3. Observe the unexpected output from the Map example where even numbers are not completely removed.
4. Run `bugSolution.kt` to see the correct usage of removeIf with Maps.

**Solution:**

The correct approach involves creating a new Map or modifying the map in place using other methods (iterating and removing entries manually).