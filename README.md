# 🔄 push_swap - Stack Sorting Algorithm

Hey there! 👋 Welcome to my push_swap project, where I tackled the fascinating challenge of sorting numbers using two stacks and a limited set of operations. Let me walk you through this algorithmic adventure!

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

This project came with some interesting challenges:

1. **Algorithm Efficiency**:
   - Finding the most efficient sorting method
   - Minimizing the number of operations
   - Handling different stack sizes efficiently

2. **Edge Cases**:
   - Dealing with negative numbers
   - Handling duplicate numbers
   - Managing invalid inputs
   - Special cases for small sets of numbers

3. **Memory Management**:
   - Proper allocation and freeing of nodes
   - Managing the linked list structure
   - Preventing memory leaks

## 🎓 What I Learned

This project was a fantastic learning experience:

1. **Algorithm Design**:
   - Understanding sorting algorithms deeply
   - Learning about algorithm optimization
   - Thinking about space and time complexity

2. **Data Structures**:
   - Working with linked lists
   - Managing complex data structures
   - Understanding stack operations

3. **Problem Solving**:
   - Breaking down complex problems
   - Optimizing solutions
   - Handling edge cases effectively

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
