<h1>ExpNo 9: Solve Wumpus World Problem using Python demonstrating Inferences from Propositional Logic</h1> 
<h3>Name:Sairam V </h3>
<h3>Register Number:212225230237</h3>
<H3>Aim:</H3>
<p>
    To solve  Wumpus World Problem using Python demonstrating Inferences from Propositional Logic
</p>
<h1>Problem Description</h1>
<hr>
<h2>Wumpus World</h2>
<hr>
The Wumpus world is a simple world example to illustrate the worth of a knowledge-based agent and to represent knowledge representation.

The figure below shows a Wumpus world containing one pit and one Wumpus. There is an agent in room [1,1]. The goal of the agent is to exit the Wumpus world alive. The agent can exit the Wumpus world by reaching room [4,4]. The wumpus world contains exactly one Wumpus and one pit. There will be a breeze in the rooms adjacent to the pit, and there will be a stench in the rooms adjacent to Wumpus.

![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/cd6b68dc-c79f-4dcb-8126-04da90d65912)

<center>Wumpus World Representation</center>
<p>
This is a python program that uses propositional logic sentences to check which rooms are safe. 

It is assumed that there will always be a safe path that the agent can take to exit the Wumpus world. The logical agent can take four actions: Up, Down, Left and Right. These actions help the agent move from one room to an adjacent room. The agent can perceive two things: Breeze and Stench.
</p>

<hr>
<h1>Sample Input and Output:</h1>
<hr>

![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/8696111a-a4a7-47cb-ba4b-43a4ef88573f)
![image](https://github.com/natsaravanan/19AI405FUNDAMENTALSOFARTIFICIALINTELLIGENCE/assets/87870499/4be5bf06-79fa-4fa0-9334-38a33f06060b)

# program:

```
from collections import deque

pit = (3, 3)
wumpus = (2, 3)
start = (1, 1)
goal = (4, 4)

def adj(c):
    x, y = c
    return [(a,b) for a,b in
            [(x-1,y),(x+1,y),(x,y-1),(x,y+1)]
            if 1 <= a <= 4 and 1 <= b <= 4]

def percept(c):
    a = adj(c)
    return pit in a, wumpus in a

q = deque([(start, [start])])
visited = {start}

while q:
    c, path = q.popleft()
    print(c, "->", percept(c))

    if c == goal:
        print("Safe Path:", path)
        break

    for n in adj(c):
        if n not in visited and n not in [pit, wumpus]:
            visited.add(n)
            q.append((n, path + [n]))

```

# output:

<img width="995" height="452" alt="image" src="https://github.com/user-attachments/assets/06f46fff-4232-415b-b57d-e9cd7e1ae87d" />


# result:
 The program was implemented using Python successfully and found the short and correct path to reach the goal.
