## SYLLABUS
- Introduction
- Language, Grammar, String Creation (valid + non valid)
- Derivation, Derivation Tree (Left most DT, Right most DT)
- Ambiguous and Non-ambiguous grammar
- Mealy M/C and Moore M/C and convertion
- NFA and DFA and conversion with & without (epsilon) closure.
- Regular expression.
- RE to Finite Automata
- Finite automata to regular expression (Arden's theorem)
- Finite automata process (testing table, testing graph, finite memory, loop-free or not
- Pumping lemma (rules 1, 2, 3)
- CNF, GNF
- CFG -> CNF -> GNF
- Left recursive grammar
- Push down automata (rules and applications)
- Turing M/C


**Formal Language:** A language which a computer can understand.

There are 2 major start and end points in a Language: *Sender* and *Receiver.*
There are steps for successful communication between the Sender and Receiver. These rules are called *protocols.*
Without protocols, communication cannot be established.

### Symbols
Symbols are an entity or individual objects, which can be any letter, alphabet or any picture, e.g. #, 1, a, b, etc.

Alphabets are a finite set of symbols. It is denoted by ==Σ== .
For example:
Σ = {a, b}
Σ = {1, 2, 3}
Σ = {A, B, C}
Σ = {#, @, $}

Lowercase set element(s) is/are called *Terminal(s)*, and uppercase set element(s) is/are called *Non-Terminal(s)*.

### Strings
It is a finite collection of symbols from the alphabet.  The string is denoted by ==ω== (terminal w/omega).
For example:
If Σ = {a, b}, various strings that can be generated from Σ are {ab, aa, aaaa, bbb, aba, bba...}
So, we write: ω = {aa, ab, aaa, aba, abaa, bba...}.

**Finite Language:** Suppose we say, L1 = {set of strings of length 2} = {aa, ab, ba, ab, bb}.
**Infinite Language**: Suppose we say, L2 = {every string that can be started with a} = {a, aa, abb, aaaa, abbab...}

### Grammar of Formal Language
- A grammar G can be formally written as a 4-tuple (N, T, S, P) where:
	1. N or Vn is a set of variables or **non-terminal** symbols.
	2. T or Σ is a set of **terminal** symbols.
	3. S is a special variable called the **Start Symbol**, S ∈ N.
	4. P is **production** rules for terminals and non-terminals. It has the rule: (α -> β), where α and β are strings on N ∪ Σ and least one symbol of a symbol of α ∈ N. 95% of times, α is a *single non-terminal*.

- Suppose the following Grammar G1: 
	({S, A}, {a, b}, S, {S -> aAb, aA -> aaAb, A -> ε}) [Epsilon is null. Not considered]
	 [N]    [T]   [S]                           [P]
	Some of the rules that can be derived are:
		S => aAb using production S -> aAb
		=> aaAbb using production aA -> aAb (not accepted)
		=> aaaAbbb using production aA -> aAb (not accepted)
		=> aaabbb using production A -> ε. (accepted)
		[S -> terminal(s) for acceptance]


#### Left Most Derivation (LMD) and Right Most Derivation (RMD)
In Grammar, we have two derivation rules, LMD and RMD. 
If working with LMD, the left-most non-terminal value will be selected, conversely in case of RMD, the right-most non-terminal value will be selected.

Create the following string from G2 using RMD: **(a * b + a)**
G2 = ({E}, {a, b}, {E}, {E -> E + E, E -> E * E, E -> a, E -> b})
	  [N]    [T]    [S]                            [P]
	E -> E * E
	   -> E * E + E
	   -> E * E + a
	   -> E * b + a
	   -> **a * b + a** [string created]

[***ALWAYS GIVE ARROW OF WHICH START TERMINAL IS BEING CHANGED***]

#### Left Most Derivation Tree (LMDT)
**1.** G : {E}, {a, b}, {E}, {E -> E + E, E -> E * E. E -> a, E -> b}
      [N]   [T]    [S]                          [P]
**LMD:**   E -> E + E
	    -> E * E + E (since, E -> E * E)
	    -> a * E + E (E -> a)
	    -> a * b + E (E -> b)
	    **E -> a * b + a** (E -> a)
![[Pasted image 20250109105825.png]]

##### Rules of Derivation Tree
1. Start symbol (non-terminal) is always **root node**.
2. Start symbol and non-terminals are denoted by **circles**.
3. After completing the tree, bound the area and mark it as "valid string".

#### Right Most Derivation Tree (RMDT) -> Same rules as LMDT
**2.** G = ({E}, {a, b}, {E}, {E -> E + E, E -> E * E, E -> a, E -> b})
	   [N]    [T]    [S]                            [P]
	E -> E * E
	   -> E * E + E
	   -> E * E + a
	   -> E * b + a
	   -> **a * b + a** [string created]
![[Pasted image 20250109110341.png]]

#### Ambiguous Grammar
**Ambiguous** means the same string with different Derivation tree (LMDT, RMDT).

1. Find whether the following grammar is ambiguous or not:
		S -> aSb | SS
		S -> ε
**Answer:** The grammar can be written as: 
		G: {S}, {a, b}, {S}, {S -> aSb, S -> SS, S -> ε}
	Here,
	N = Non-terminals (S)
	T = terminals (a, b)
	S = start symbol (S)
	P = Production rules (S -> aSb, S -> SS, S -> ε)

**LMD**:	S -> *S*S
		-> a*S*bS (since, S -> aSb)
	    -> a*S*SbS (since, S -> SS)
	    -> aa*S*bSbS (since, S -> aSb)
	    -> aab*S*bS (since, S -> ε)
	    -> aabb*S* (since, S -> ε)
    S -> **aabb** (since, S -> ε)

**RMD**: S -> S*S*
	    -> Sa*S*b (S -> aSb)
	    -> SaS*S*b (S -> SS)
	    -> SaSa*S*bb (S -> aSb)
	    -> Sa*S*abb (S -> ε)
	    -> *S*aabb (S -> ε)
	S -> **aabb** (S -> ε)

Since the string in LMD and RMD are equal, the grammar is ambiguous.

### Finite Automata
#### What is Automata?
The word **automata** comes from the Greek word, *autoquata* which means *self acting*.
It defines a whole lot of different processes, like:
1. Computation process
2. Abstract process
3. Statistical and mathematical process
4. Application base operation
5. Automatic system
*A finite automata, for example, shows and defines the all the steps a computer does between taking input and storing it into its memory.*

There are 2 types of automata:
1. **Deterministic Finite Automata (DFA)**
2. **Non-deterministic Finite Automata (NFA)**

In finite automata, the symbols are:
**Finite Automata has 5-tuples (Q, Σ, δ, qₒ, F), where:**
1. Q = {set of states}
2. Σ = {input alphabets}
3. δ = {transition array/transition diagram}
4. qₒ = Initial state
5. F = Final state

![[WhatsApp Image 2025-01-10 at 11.40.20 AM.jpeg]]
In the above diagram
Q = {$q_0, q_1, q_2, q_3$}
Σ = {0, 1}
δ = 
q = $q_0$
F = {}

1. canvart NFA to DFA
   step 1: write in tapal format
   step 2: given NFA diagram to NFA transition table .

| States | a = 0 | a = 1 |
| ------ | ----- | ----- |
| q0 =   |       |       |
step 3. NFA TT to DFA TT

| States | a = 0 | a = 1 |
| ------ | ----- | ----- |
| q0 =   |       |       |

#### NFA to DFA without using ε closure