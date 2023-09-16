TOPIC : [[STACKS]]
`2023-07-12

## TOPIC INFO 
There are `n` cars going to the same destination along a one-lane road. The destination is `target` miles away.

You are given two integer array `position` and `speed`, both of length `n`, where `position[i]` is the position of the `ith` car and `speed[i]` is the speed of the `ith` car (in miles per hour).

A car can never pass another car ahead of it, but it can catch up to it and drive bumper to bumper **at the same speed**. The faster car will **slow down** to match the slower car's speed. The distance between these two cars is ignored (i.e., they are assumed to have the same position).

A **car fleet** is some non-empty set of cars driving at the same position and same speed. Note that a single car is also a car fleet.

If a car catches up to a car fleet right at the destination point, it will still be considered as one car fleet.

Return _the **number of car fleets** that will arrive at the destination_.



so basically when i did this i was doing some wierd shit but i then started moving towards plotting the equations and then thought of doing it mathematically and then just got bored and saw the solution i really need to strat typing shit bro like for the last 4 questions i havent been coding anything ok so the solution was  that first you make a tuple list type thing from the given arrays and then you sort it according to the position and start fro the position most ahead and then you push stuff to a stack and everytime you push you check if the top of the stack is reaching earlier or later than the car in question if the top of stack reaches later you dont push the current car to the stack and if the car in question reaches later then you push it therefore the number of elements in the stack by the end of the program is the number of fleet present.

```python
class Solution:

def carFleet(self, target: int, position: List[int], speed: List[int]) -> int:

pair = [(p, s) for p, s in zip(position, speed)]

pair.sort(reverse=True)

stack = []

for p, s in pair: # Reverse Sorted Order

stack.append((target - p) / s)

if len(stack) >= 2 and stack[-1] <= stack[-2]:

stack.pop()

return len(stack)
```



### BRIEF



### CONCLUSION