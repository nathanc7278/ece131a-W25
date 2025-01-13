# Sample Space. Set Properties. Axioms of Probability

## Sample Spaces

`Random Experiment` an experiment in which the result is unpredictable under repeated conditions.

Example: Tossing a fair coin. Observe heads or tails.

* has an experimental procedure
* set of observations

`Sample Space` the collection of all possible outcomes of a random experiment.

`Outcome` a result of a random experiment that cannot be decomposed in terms of results. Exactly one outcome occurs.

Suppose we toss a coin 3 times.

$$S = \{HHH, HHT, HTH, THH, TTH, THT, HTT, TTT\}$$

$S$ is the sample space associated with this experiment . NOte that outcomes are mutually exclusive and collectively exhaustive representation of a given random experiment.

$|S|$ represents the `cardinality` of a set. The cardinality is the number of elements in a set.

Example: Describe the following outcomes

* the number of heads is 1
* the number of heads is 2
* the number of heads is 3

$$
E_1 = \{HTT, THT, TTH\}\newline
E_2 = \{HHT, HTH, THH\}\newline
E_3 = \{HHH\}\newline
 \text{$E_3$ is an elementary event}
$$

`Event` a set of outcomes that share a particular property. An event is called `elementary` if it is described by just one outcome.

## Set Theory

Let $A$ and $B$ denote two events (two sets of outcomes of some random experiment)

`union` $A\cup B$ is a set of all outcomes either in $A$ or $B$.

`intersection` $A\cap B$ is a set of all outcomes that are in both $A$ and $B$

if $A\cap B = \emptyset$ then events $A$ and $B$ are mutually exclusive.

`compliment` $A^C$ is the set of all outcomes in $S$ that are not in $A$

`subset` $A\subseteq B$ is a subset of $B$ if every outcome in $A$ is also an outcome in $B$.

if $A\subseteq B$ and $B\subseteq A$ then $A=B$

`set difference` $A\backslash B$ is the set of all outcomes that are in A but not in B.

### Set Properties

1. **Commutativity**

$$
A\cup B = B\cup A\newline
A\cap B = B\cap A
$$

2. **Associativity**

$$
(A\cup B)\cup C = A \cup (B\cup C)\newline
(A\cap B)\cap C = A \cap (B\cap C)
$$

3. **Distributivity**

$$
(A\cup B)\cap C = (A\cap C)\cup (B\cap C)\newline
(A\cap B)\cup C = (A\cup C)\cap (B\cup C)
$$

4. **DeMorgan's Laws**

$$
(A\cup B)^C = A^C\cap B^C\newline
(A\cap B)^C = A^C\cup B^C
$$

## Axioms of Probability and Important Consequences

**Probability law** is the rule that assigns probability to ever event associated with a random experiment.

Such law must satisfy the following Axioms:

1. $P(A) \geq 0$ where $A$ is any event of a random experiment

2. $P(S) = 1$ where $S$ denotes a sample space

3. If $A\cap B = \emptyset$ then $P(A\cup B) = P(A) + P(B)$

### Some Important Consequences

$P(A)$ is given
* $P(A^C) = 1 - P(A)$

$$
P(S) = 1\newline
S = A\cup A^C\newline
A\cap A^C = \emptyset\newline
P(S)=P(A\cup A^C) = P(A) + P(A^C)\newline
1 = P(A) + P(A^C)\newline
P(A^C) = 1 - P(A)
$$

* $P(A) \leq 1$

$$
P(A^C) = 1 - P(A)\newline
P(A^C) \geq 0 \;\text{and}\; P(A) \leq 1\newline
0 \leq P(A) \leq 1
$$

* $P(\emptyset) = 0$

$$
S^C = \emptyset\newline
S\cup S^C = S
$$

Example: Consider $A_1, A_2, A_3,...,A_n$ such that they are `pair-wise mutually exclusive`:

$$ A_i, A_j \;\forall\; 1\leq i, 1\leq j\newline
i \ne j\newline
A_i\cap A_j = \emptyset
$$

**Corollary:**

$P(\cup^{n}_{k=1}A_k) = \sum^{n}_{k=1}P(A_k)$

Consider $n=2$

$A_1$ and $A_2$ are mutually exclusive

$P(A_1 \cup A_2) = P(A_1) + P(A_2)$

Base Case true by Axiom 3.

For the general case: `proof by induction`

* base case
* inductive hypothesis (assume true for n and prove it is true for n+1)

**Proof**:

Assume $P(\cup_{k=1}^{n}A_k) = \sum_{k=1}^{n}P(A_k)$

we need to show: $P(\cup_{k=1}^{n+1}A_k) = \sum_{k=1}^{n+1}P(A_k)$

Consider $P(\cup_{k=1}^{n+1}A_k) = P(\{\cup_{k=1}^{n}A_k\}\cup A_{n+1})$

Let $B_n = \cup_{k=1}^{n}A_k$

* justification: we need to show $B_n$ and $A_{n+1}$ are mutually exclusive

$$
A_1 \cap A_{n+1} = \emptyset\newline
A_2 \cap A_{n+1} = \emptyset\newline
\vdots\newline
A_n \cap A_{n+1} = \emptyset\newline
$$

$$
\{\cup^{n}_{k=1} A_k\} \cap A_{n+1}= \emptyset\newline
\therefore P(\cup^{n}_{k=1}A_k) + P(A_{n+1}) = \sum^{n}_{k=1}P(A_k)+P(A_{n+1}) \newline
=  \sum^{n+1}_{k=1}P(A_k)
$$

Now suppose $A$ and $B$ are not necessarily mutually exclusive. Then:

$$
P(A\cup B) = P(A) + P(B) - P(A\cap B)
$$
