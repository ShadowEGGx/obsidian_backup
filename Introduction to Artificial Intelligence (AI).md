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

