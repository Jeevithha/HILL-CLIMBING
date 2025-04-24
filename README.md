# ExpNo 5 : Implement Simple Hill Climbing Algorithm
## Name: Jeevitha S
## Register Number: 212222100016
## Aim:
Implement Simple Hill Climbing Algorithm and Generate a String by Mutating a Single Character at each iteration

## Theory:
Hill climbing is a variant of Generate and test in which feedback from test procedure is used to help the generator decide which direction to move in search space. Feedback is provided in terms of heuristic function

## Algorithm:

Evaluate the initial state.If it is a goal state then return it and quit. Otherwise, continue with initial state as current state.
Loop until a solution is found or there are no new operators left to be applied in current state:
Select an operator that has not yet been applied to the current state and apply it to produce a new state
Evaluate the new state:
if it is a goal state, then return it and quit
if it is not a goal state but better than current state then make new state as current state
if it is not better than current state then continue in the loop
Steps Applied:
Step-1
Generate Random String of the length equal to the given String

Step-2
Mutate the randomized string each character at a time

Step-3
Evaluate the fitness function or Heuristic Function

Step-4:
Lopp Step -2 and Step-3 until we achieve the score to be Zero to achieve Global Minima.

## PROGRAM

```
import random
import string

def generate_random_solution(answer):
    l = len(answer) 
    return [random.choice(string.printable) for _ in range(l)]

def evaluate(solution, answer):
    print("Solution:", "".join(solution))
    target = list(answer)
    diff = 0
    for i in range(len(target)):
        s = solution[i]
        t = target[i]
        diff += abs(ord(s) - ord(t))
    return diff

def mutate_solution(solution):
    ind = random.randint(0, len(solution) - 1)
    solution[ind] = random.choice(string.printable)
    return solution

def SimpleHillClimbing():
    answer = "Artificial Intelligence"
    best = generate_random_solution(answer)
    best_score = evaluate(best, answer)
    while True:
        print("Score:", best_score, "Solution:", "".join(best))
        if best_score == 0:
            break
        new_solution = mutate_solution(list(best))
        score = evaluate(new_solution, answer)
        if score < best_score:
            best = new_solution
            best_score = score


#answer = "Artificial Intelligence"
#print(generate_random_solution(answer))
#solution = generate_random_solution(answer)
#print(evaluate(solution, answer))
```

### SimpleHillClimbing()
Sample Input and Output
## Sample String:
Artificial Intelligence
## Output:
Score: 643 Solution : 8RzF:oG ]%;CPORRMe!zGvk
Score: 609 Solution : 8RzF:oG ]%;CPqRRMe!zGvk
Score: 604 Solution : 8RzF:oG ]%;CPqRRMe!zGqk
Score: 594 Solution : 8RzF:oG ]%;CPqRRWe!zGqk
Score: 551 Solution : 8RzF:oGK]%;CPqRRWe!zGqk
Score: 551 Solution : 8RzF:oGK]%;CPqRRWe!zGqk
Score: 551 Solution : 8RzF:oGK]%;CPqRRWe!zGqk
Score: 551 Solution : 8RzF:oGK]%;CPqRRWe!zGqk
Score: 551 Solution : 8RzF:oGK]%;CPqRRWe!zGqk
....................................................
..................................................
................................................
Score: 1 Solution : Artificial Intelligencf
Score: 1 Solution : Artificial Intelligencf
Score: 1 Solution : Artificial Intelligencf
Score: 1 Solution : Artificial Intelligencf
Score: 0 Solution : Artificial Intelligence
## OUTPUT
![image](https://github.com/user-attachments/assets/1d1c1dff-505d-4cc3-b40c-e2d066c3480d)


## RESULT
Thus the Simple Hill Climb Algorithm Implemented successfully.
