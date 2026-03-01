Data Structures and Algorithms

#Question
Write a function tigger_value() to calculate the final value of tigger after performing a list of operations.
•	The function accepts a list operations containing strings.
•	There are four possible operations:
o	"bouncy" and "flouncy" → increment tigger by 1
o	"trouncy" and "pouncy" → decrement tigger by 1
•	Initially, tigger = 1.
•	The function should return the final value of tigger.
________________________________________
Walkthrough of the question
We are given a list of operations that either increase or decrease tigger. We need to apply all operations in order, keeping track of the current value of tigger.
This is a typical array question because we are iterating over a list of strings.
________________________________________
Edge cases to consider
1.	Empty list → should return 1 (tigger’s initial value)
2.	All increment operations → tigger increases correctly
3.	All decrement operations → tigger decreases correctly
4.	Mixed operations → tigger goes up and down in sequence
5.	Large number of operations → solution should handle efficiently
6.	Invalid strings → can be ignored (optional, based on problem assumptions)
________________________________________
Approach chosen
Linear traversal with conditional updates
•	Read each operation one by one
•	Update tigger depending on the operation type
Trade-off: Simplicity over performance. Linear traversal is O(n), but it’s simple and works for any list size.
________________________________________
Algorithm/Brute Force
Step 1: Start with tigger = 1.
Step 2: Loop through each element in the list of operations.
Step 3: If the operation is "bouncy" or "flouncy", increment tigger by 1.
Step 4: If the operation is "trouncy" or "pouncy", decrement tigger by 1.
Step 5: Repeat until all operations are applied.
Step 6: Return the final value of tigger.
________________________________________
Code in Python
def tigger_value(operations):
    tigger = 1  # initial value

    for op in operations:
        if op == "bouncy" or op == "flouncy":
            tigger += 1
        elif op == "trouncy" or op == "pouncy":
            tigger -= 1
        # ignore any invalid strings

    return tigger
________________________________________
Time Complexity
•	Worst case: O(n) → must check each operation once.
•	Best case: O(n) → even if all increments are first, we still need to read the full list. Unlike linear search where best case can be O(1), here we must process all operations.
________________________________________
Space Complexity
•	O(1) → we only store a single variable tigger
•	No additional data structures are required
________________________________________
Trade-offs
•	Simplicity: Linear traversal is straightforward, easy to implement, and easy to understand.
•	Performance: Efficient enough for small or medium lists. If operations were extremely large, optimizations (like pre-counting increments and decrements) could reduce time slightly.
•	Alternative approaches: Could use count() on the list (built-in), but the question may forbid built-ins.
