# PUSH SWAP

This project involves sorting data on a stack, with a limited set of instructions, and the smallest number of moves. To
make this happen, you will have to manipulate various sorting algorithms and choose the most appropriate solution(s) for
optimized data sorting



# Sorting with Two Stacks

## Overview
This document describes the use of two stacks (`a` and `b`) to sort the contents of stack `a` in ascending order. The sorting process involves a series of predefined actions, which manipulate the stacks to achieve the desired order.

### Initial Setup
- **Stack `a`**: Contains a random number of unique integers (negative and/or positive).
- **Stack `b`**: Initially empty.

### Goal
Sort the integers in **stack `a`** in ascending order.

---

## Actions

### `sa` (swap a)
Swaps the top two elements of stack `a`. If stack `a` has fewer than two elements, this operation does nothing.

#### Example:
Before:
```
Stack a: [3, 2, 5, 8]
Stack b: []
```
After `sa`:
```
Stack a: [2, 3, 5, 8]
Stack b: []
```

### `sb` (swap b)
Swaps the top two elements of stack `b`. If stack `b` has fewer than two elements, this operation does nothing.

#### Example:
Before:
```
Stack a: []
Stack b: [7, 1, 4]
```
After `sb`:
```
Stack a: []
Stack b: [1, 7, 4]
```

### `ss`
Performs `sa` and `sb` simultaneously.

#### Example:
Before:
```
Stack a: [3, 2, 5]
Stack b: [7, 1, 4]
```
After `ss`:
```
Stack a: [2, 3, 5]
Stack b: [1, 7, 4]
```

### `pa` (push a)
Moves the top element of stack `b` to the top of stack `a`. Does nothing if stack `b` is empty.

#### Example:
Before:
```
Stack a: [3, 2, 5]
Stack b: [7, 1]
```
After `pa`:
```
Stack a: [7, 3, 2, 5]
Stack b: [1]
```

### `pb` (push b)
Moves the top element of stack `a` to the top of stack `b`. Does nothing if stack `a` is empty.

#### Example:
Before:
```
Stack a: [3, 2, 5]
Stack b: [7]
```
After `pb`:
```
Stack a: [2, 5]
Stack b: [3, 7]
```

### `ra` (rotate a)
Shifts all elements of stack `a` up by one. The first element becomes the last element.

#### Example:
Before:
```
Stack a: [3, 2, 5, 8]
Stack b: []
```
After `ra`:
```
Stack a: [2, 5, 8, 3]
Stack b: []
```

### `rb` (rotate b)
Shifts all elements of stack `b` up by one. The first element becomes the last element.

#### Example:
Before:
```
Stack a: []
Stack b: [7, 1, 4]
```
After `rb`:
```
Stack a: []
Stack b: [1, 4, 7]
```

### `rr`
Performs `ra` and `rb` simultaneously.

#### Example:
Before:
```
Stack a: [3, 2, 5]
Stack b: [7, 1, 4]
```
After `rr`:
```
Stack a: [2, 5, 3]
Stack b: [1, 4, 7]
```

### `rra` (reverse rotate a)
Shifts all elements of stack `a` down by one. The last element becomes the first element.

#### Example:
Before:
```
Stack a: [3, 2, 5, 8]
Stack b: []
```
After `rra`:
```
Stack a: [8, 3, 2, 5]
Stack b: []
```

### `rrb` (reverse rotate b)
Shifts all elements of stack `b` down by one. The last element becomes the first element.

#### Example:
Before:
```
Stack a: []
Stack b: [7, 1, 4]
```
After `rrb`:
```
Stack a: []
Stack b: [4, 7, 1]
```

### `rrr`
Performs `rra` and `rrb` simultaneously.

#### Example:
Before:
```
Stack a: [3, 2, 5]
Stack b: [7, 1, 4]
```
After `rrr`:
```
Stack a: [5, 3, 2]
Stack b: [4, 7, 1]
```

---

## Quicksort Implementation
You implemented the sorting algorithm using the **Quicksort** technique. Quicksort is a highly efficient, divide-and-conquer sorting algorithm that works as follows:

### Algorithm Steps
1. **Choose a Pivot**: Select an element from the stack as the pivot.
2. **Partitioning**:
   - Move elements smaller than the pivot to one stack (`b`), leaving elements greater than or equal to the pivot in stack `a`.
3. **Recursive Sorting**:
   - Recursively sort the two partitions.
4. **Merge**:
   - Combine the sorted partitions back into stack `a` in ascending order.

### Advantages of Quicksort
- **Time Complexity**: 
  - **Best/Average Case**: O(n log n)
  - **Worst Case**: O(n^2) (occurs when the pivot selection is poor, e.g., always the smallest or largest element)
- **Space Efficiency**: Requires minimal additional space compared to other divide-and-conquer algorithms like Merge Sort.

### Example
Given:
```
Stack a: [3, -1, 4, 1, 5]
Stack b: []
```

**Step 1**: Choose pivot (e.g., 3).
- Move elements smaller than 3 to stack `b`.
```
Stack a: [3, 4, 5]
Stack b: [-1, 1]
```

**Step 2**: Recursively sort both stacks.
- Sort `[3, 4, 5]` and `[-1, 1]`.

**Step 3**: Merge sorted stacks back into `a`.
```
Stack a: [-1, 1, 3, 4, 5]
Stack b: []
```

---

## Time Complexity

### Key Operations
- **Swap Operations (`sa`, `sb`, `ss`)**:
  - **Time Complexity**: O(1)
  - Swapping the top two elements is a constant-time operation.

- **Push Operations (`pa`, `pb`)**:
  - **Time Complexity**: O(1)
  - Moving the top element between stacks is a constant-time operation.

- **Rotate Operations (`ra`, `rb`, `rr`)**:
  - **Time Complexity**: O(n)
  - Each element in the stack needs to be shifted.

- **Reverse Rotate Operations (`rra`, `rrb`, `rrr`)**:
  - **Time Complexity**: O(n)
  - Each element in the stack needs to be shifted.

### Overall Sorting Complexity
The use of Quicksort ensures an average complexity of **O(n log n)**, with worst-case scenarios being **O(n^2)** if the pivot selection is poor.

---

