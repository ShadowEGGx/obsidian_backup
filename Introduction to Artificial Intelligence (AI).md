### History of AI
in 1950, a scientist named *Alan Turing* created a machine (named *Turing Machine*), which could ask many questions to the user, the user couldn't say which question was asked by a human or the machine. It could determine the intelligence of the user. This was called **Turing Test**.

AI is said to a **multi-agent** system.

### What is an Agent?
Any living or non-living object is an agent. Agents can have various types. 
Every agent has its own goals and objectives, i.e. their own roles.

Agents are needed to solve *problems.*

#### Key components and features of an Agent
**Components**
1. It has sensors, actuators and goal.
2. It converts percept signals into actions.
3. While in current state, the agent independently plans and maximises the chance of meeting the goal.

**Features**
1. Reactiveness, i.e. response to physical stimuli.
2. Proactiveness, i.e. time bound to complete a goal.
3. Social Ability, i.e. has to be aware of the surroundings.
4. Self Learning, i.e. it learns by itself.
5. Movable.
6. Self Governing.

#### How to solve Problems?
Problem solving have the following steps:
- *Understand* the problem statement.
- *Define* the problem and *formulate* the problem.
- Find out the *methodologies* (choose a suitable workflow) to create a solution.
- *Testing* and *validation*.
- Result and analysis.
- Implementation.

##### Example to demonstrate problem solving.
Suppose we have a travelling salesman, who has to go from a city A to a city B. City A is the **start state** and City B is the **goal state**. He can have many routes to do his task. Suppose a route takes the least time, but costs him more. Another path takes considerable time, but is much cheaper. And there is another path which is an intermediate between the two. Among many paths from A to B, the above 3 are the best paths for him.
So any path he takes is an optimal solution for him. It may be represented in the following ways:
- **Pareto Curve:** 
- **State Space:**
- **Gradient Descent Method:**
	Suppose, the optimal solution is not reached, hence the solution we have is called the *local solution*. So we do *exploitation* which is making a random change in the solution with a low success probability, i.e. jumping from local solution to the optimal solution. After exploiting we do *exploration* to again check for the path to reach the optimal solution.

#### Rational Agent
A **rational agent** is an entity that perceives its environment and takes actions to achieve its goals in the most effective way possible. It is designed to operate autonomously, making decisions based on available information and striving to maximise its performance.

##### Key characters of a Rational Agent
- **Perception**: A rational agent senses the environment through **sensors** (e.g., cameras, microphones, software inputs).
- **Action**: The agent performs actions through its **actuators** (e.g., motors, displays, software outputs) to affect the environment.
- **Performance Measure**: It processes the information, evaluates potential actions, and selects the most suitable one based on a set of criteria.
- **Rationality:** Takes the action that maximises its performance based on the available information and its built-in knowledge.
- **Learning Curve:** It can learn new information and rectify its decisions with respect to the situation.

Remember the characters of a Rational Agent by the following:
**P-E-A-S**, where:
- **P** = Performance Measure
- **E** = Environment
- **A** = Actuators
- **S** = Sensors

#### Types of Agents
1. **Simple Reflex Agent**
	- Act based on current perceptions only.
	- Do not consider the history of previous states.
	- *Example*: A thermostat that turns on/off based on temperature.
	![[Pasted image 20250108094833.png]]
2. **Model-based Reflex Agent**
	- Maintain an internal state that reflects part of the environment's history.
	- Use this model to make better decisions.
	- *Example*: A robot vacuum that remembers the layout of a room.
	![[Pasted image 20250108095000.png]]
3. **Goal-Based Agent**
	- Act to achieve specific goals, which guide their decision-making process.
	- Require reasoning to determine how to achieve the goal.
	- *Example*: A pathfinding algorithm that finds the shortest route to a destination.
	![[Pasted image 20250108100212.png]]
4. **Utility-Based Agent**
	- Optimise decisions based on a utility function that quantifies the "desirability" of different outcomes.
	- *Example*: A recommendation system that suggests products based on user preferences.
	![[Pasted image 20250108100952.png]]
5. **Learning Agent**
	- Improve their performance over time by learning from the environment.
	- Adapt to changes in the environment and improve their decision-making strategies.
	- *Example*: Autonomous cars that improve driving through reinforcement learning.
	![[Pasted image 20250108101737.png]]

#### Problem Formulation
A *problem solving agent* have the following agendas:
- They are **goal oriented**.
- They measure their performance.

A problem solving agent have the following phases:
- Problem Formulation
- Searching for a solution.
- Action Execution

1. **Problem formulation** is the process of deciding what deciding what actions it needs to consider while searching for a goal.
2. The process of looking for a sequence of action to reach a goal is called **searching for solution**.
3. **Action Execution** is the set of all possible actions the agent can perform.

Problem formulation has the following stages:
1. **Initial stage, S** 
	- the starting state
2. **Action**
	- whatever path the agent chooses 
	- returns the state of actions from all possible actions from S. 
	- Written as *ACTIONS(S) = {a1, a2}*
3. **Transition Model** 
	- the set of all actions the agent does 
	- *RESULT(S, a1) = S2; RESULT(S, a2) = S3*
4. **State Space**
	- A path in the state space is a sequence of states connected by a sequence of actions.
	- *STATE SPACE = {S2, ... S9}*
5. **Goal Test** 
	- Whatever path the agent chooses to reach it's goal.
6. **Path Cost**
	- A function that assigns a numeric cost to each path.
	- The agent chooses a cost function that reflects its own performance measure.
	- *Cost of a path = a2 + a3 + a4*
	- *Step cost = C(S, a, S')*. In light of the diagram, here *Step cost = C(S, a1, a2)*
	![[Pasted image 20250110102938.png]]

##### Vacuum Cleaning Problem
The *Vacuum Cleaner Problem* is a classic example used in AI to demonstrate the operation of **intelligent agents** in a simple, well-defined environment. It focuses on how an agent can perceive its environment, take actions, and achieve its goal efficiently.

1. **Environment**
	- The vacuum cleaner operates in a 2D world with **two rooms** (labelled A and B).
	- Each room can be either:
	    - **Clean**.
	    - **Dirty**.
	- The vacuum cleaner can be located in either room at any given time.

2. **Initial State**:
	- The environment's initial state is defined by:
	    - The **position** of the vacuum cleaner (e.g., in room A).
	    - The **cleanliness** of the two rooms (e.g., A = Dirty, B = Clean).

3. **Actions**:
	- The vacuum cleaner can perform the following actions:
		- **Move Left**: If the vacuum is in room B, it can move to A.
		- **Move Right**: If the vacuum is in room A, it can move to B.
		- **Clean**: If the vacuum is in a dirty room, it cleans that room.

4. **Successor Function**:
	- The successor function specifies the resulting state after the agent performs an action.
	- Example:
	    - If the vacuum is in A and A is dirty, performing the "Clean" action will result in A = Clean.

5. **Goal Test**:
	- The goal is achieved when **both rooms are clean**, regardless of the vacuum's position.

6. **Path Cost**:
	- Assume 1 for each action

**Suppose:**
- **Initial State**:
    - Vacuum cleaner is in A.
    - A = Dirty, B = Dirty
- **Solution**:
    1. Clean in A → A = Clean, B = Dirty.
    2. Move to B → Vacuum in B, A = Clean, B = Dirty.
    3. Clean in B → A = Clean, B = Clean
- **Path Cost**: 3 actions.

##### 8 Puzzle Problem
**Initial State** (S):

| 7   | 2   | 4   |
| --- | --- | --- |
| 5   |     | 6   |
| 8   | 3   | 1   |

**Goal State** (G):

|     | 1   | 2   |
| --- | --- | --- |
| 3   | 4   | 5   |
| 6   | 7   | 8   |

**Actions:**
The possible actions for the agent (the blank space) are:
1. **Up**: Move the blank space up (swap it with the tile above).
2. **Down**: Move the blank space down (swap it with the tile below).
3. **Left**: Move the blank space left (swap it with the tile to the left).
4. **Right**: Move the blank space right (swap it with the tile to the right).

**Transition Model:**
The **transition model** specifies how the state changes when an action is applied.  
For example:
- If the blank space is at (1,2)(1, 2)(1,2) and the action is "Down," the new state will be:
​7 | 5 | 8
​2 | 6 |
3​ | 4 | 1​
​
**State Space:**
The **state space** is the set of all possible configurations of the 8-puzzle.  
Each state is a unique permutation of the tiles {1, 2, 3, 4, 5, 6, 7, 8, ...}.
A **path in the state space** is a sequence of states connected by actions (e.g., Up, Down, Left, Right) starting from the initial state and ending at the goal state.

**Path Cost:**
The **path cost** is the total cost of the sequence of actions taken to reach the goal state.
- Each action (Up, Down, Left, Right) has a **step cost of 1**.
- The **total path cost** is the number of moves required to solve the puzzle.


#### Solution Searching
After formulating the problem, we have to *search* for a solution. There are two types of searching mechanisms:
- Informed
- Uninformed

##### Close World Assumption
1. A statement that is true is also known to be true.
2. All the necessary information about the problem domain is available in percept so that each state is a complete description of the world.
3. No incomplete information at any point of time.