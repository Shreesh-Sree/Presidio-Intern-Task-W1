# DSA Modules - Developer Activity & Recursion Analysis

This document analyzes the DSA components implemented in `DevInsight-Lab`.

## 1. HashMap Modules (Frequency Counters)

### log_analyzer.py
- **Purpose**: Parses a stream/list of developer activity logs (e.g. commits, reviews, pull requests) and aggregates frequency counts per action and per developer.
- **Key Operations**:
  - Initializing frequency maps (dictionaries).
  - Counting commit, PR, and review events.
- **Complexity**:
  - **Time Complexity**: $O(N)$ where $N$ is the number of log events. Dictionary insertions and lookups are $O(1)$ on average.
  - **Space Complexity**: $O(D + E)$ where $D$ is unique developers and $E$ is unique event types.

### contributor_frequency.py
- **Purpose**: Generates a leaderboard ranking contributors by their commit frequency.
- **Complexity**:
  - **Time Complexity**: $O(N \log N)$ where $N$ is the number of developers (due to sorting the leaderboard).
  - **Space Complexity**: $O(N)$ to store rankings.

---

## 2. Recursion Modules (Tree Traversals)

### folder_analyzer.py
- **Purpose**: Recursively walks a directory structure to analyze folder sizes and structure.
- **Key Operations**:
  - Recursive folder checks and file counting.
- **Complexity**:
  - **Time Complexity**: $O(F + V)$ where $F$ is folders and $V$ is files.
  - **Space Complexity**: $O(D)$ where $D$ is the maximum depth of the directory structure (recursion stack).

### dependency_traversal.py
- **Purpose**: Recursively resolves module dependencies to determine compilation or execution order.
- **Complexity**:
  - **Time Complexity**: $O(V + E)$ (Depth-First Search graph traversal).
  - **Space Complexity**: $O(V)$ for recursion stack and visited set.
