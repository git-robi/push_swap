# 🔄 push_swap - Stack Sorting Algorithm

Hey there! 👋 Welcome to my push_swap project, where I tackled the challenge of sorting numbers using two stacks, a limited set of operations and the most suitable algorithm.

## 🎯 What's This Project About?

Imagine you have a stack of numbers and you need to sort them, but here's the catch:
- You have two stacks (let's call them stack A and stack B)
- You can only use specific operations to manipulate these stacks
- You need to sort the numbers using the minimum possible number of moves

The allowed operations are:
- `sa` (swap a): Swap the first 2 elements of stack A
- `sb` (swap b): Swap the first 2 elements of stack B
- `ss`: Do `sa` and `sb` at the same time
- `pa` (push a): Take the first element from B and put it on top of A
- `pb` (push b): Take the first element from A and put it on top of B
- `ra` (rotate a): Shift up all elements of stack A by 1
- `rb` (rotate b): Shift up all elements of stack B by 1
- `rr`: Do `ra` and `rb` at the same time
- `rra` (reverse rotate a): Shift down all elements of stack A by 1
- `rrb` (reverse rotate b): Shift down all elements of stack B by 1
- `rrr`: Do `rra` and `rrb` at the same time

## 🛠️ How I Built It

I implemented this project using the Turk algorithm, adapting it to work with linked lists for better efficiency:

1. **The Turk Algorithm Approach**:
   - Push all numbers except 3 to stack B
   - Sort the remaining 3 numbers in stack A
   - Find the best position in stack A for each number in stack B
   - Calculate the cost of moving each number to its position
   - Move the cheapest number from B to A
   - Repeat until stack B is empty
   - Final rotation to put the smallest number on top

2. **Data Structure**:
   - Implemented using doubly-linked lists for both stacks
   - Each node contains:
     - The actual value
     - Its index in the sorted sequence
     - Cost information for moving it
     - Target position information
     - Is_below_middle flag for optimization
     - Pointers to next and previous nodes

3. **Cost Optimization**:
   - Calculate rotation costs for both stacks
   - Find the cheapest combination of moves
   - Use combined operations (`rr`, `rrr`) when rotating both stacks
   - Keep track of middle positions to optimize rotations
   - Mark the most efficient moves as 'cheapest'

## 🤔 The Tricky Parts

Developing push_swap presented unique challenges in algorithm design and optimization. Each challenge pushed me (no pun intended) to think creatively about efficient solutions while maintaining code reliability.

### Algorithm Optimization
The core challenge lay in developing an efficient sorting strategy with minimal operations. My implementation of the Turk algorithm required careful optimization to handle various stack sizes effectively. I focused on minimizing the number of moves while ensuring the solution remained robust across different input sizes. This involved analyzing operation patterns and finding opportunities to combine moves, ultimately leading to a more efficient sorting process.

### Edge Case Management
Handling diverse input scenarios proved crucial for reliability. My system robustly manages negative numbers and duplicates, ensuring consistent behavior across all input types. I developed specialized approaches for small datasets, where the standard algorithm might be inefficient. The input validation system carefully screens for invalid entries while maintaining optimal performance, making the program both reliable and efficient.

### Memory Architecture
Implementing a doubly-linked list structure required careful attention to memory management. I designed a comprehensive system for tracking node allocations and deallocations, ensuring proper cleanup during all operations. Special attention was paid to maintaining list integrity during complex sorting operations, preventing memory leaks while preserving performance.

## 🎓 What I learnt

This project provided deep insights into algorithm design and data structure implementation, significantly expanding my understanding of efficient programming practices.

### Algorithm Design Principles
Working with the Turk algorithm deepened my understanding of sorting strategies and their optimizations. I learned to analyze algorithms not just for correctness, but for operation count and efficiency. This experience taught me to think critically about algorithmic choices and their impact on performance, especially when working with constrained operations.

### Data Structure Implementation
Implementing stacks using doubly-linked lists provided practical experience in complex data structure design. I learned to balance the tradeoffs between different implementation approaches, considering both performance and maintainability. The project demonstrated how the right data structure choice can significantly impact algorithm efficiency.

### Problem-Solving Methodology
The project reinforced systematic problem-solving approaches in algorithm development. I learned to decompose complex sorting challenges into manageable components, optimize each part individually, and integrate them into a cohesive solution. This experience emphasized the importance of thorough testing and continuous refinement in developing robust algorithms.

## 💡 How to Use It

```bash
# Compile the program
make

# Run with numbers as arguments
./push_swap 2 1 3 6 5 8

# Run with a string of numbers
./push_swap "2 1 3 6 5 8"

# Check the number of operations
./push_swap 2 1 3 6 5 8 | wc -l
```

## 📊 Performance

My implementation achieves these results:
- 3 numbers: ≤ 3 operations
- 5 numbers: ≤ 12 operations
- 100 numbers: ≤ 700 operations
- 500 numbers: ≤ 5500 operations

These results are very good because they're below the thresholds required for the bonus points, demonstrating the efficiency of my implementation.

### 🐛 Error Handling

The program handles various error cases:
- Invalid arguments (non-numbers, out of integer range)
- Duplicate numbers
- Memory allocation failures
- Empty input
## 🔍 Final Thoughts

This project was a great exercise in algorithmic thinking and optimization. It's fascinating how a seemingly simple problem (sorting numbers) becomes much more complex when you're limited to specific operations.

The skills I learned here - especially about algorithm optimization and data structure manipulation - have been invaluable for understanding how to approach complex programming challenges. Plus, it's pretty satisfying to watch those numbers get sorted efficiently! 🎯

---
*Built with ❤️ and lots of coffee at 42 School*
