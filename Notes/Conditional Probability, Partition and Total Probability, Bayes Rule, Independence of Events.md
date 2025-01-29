# Conditional Probability, Partitions and Total Probability, Bayes Rule,and Independence

## Conditional Probability

For an event $B$:

$$
P(B) > 0
$$
$$
P(A|B) = \frac{P(A\cap B)}{P(B)}
$$

$P(A|B)$ denotes: Probability that $A$ occurs given that $B$ occurs.

If $P(B)=0$ then $P(A|B)=0$

Example 1: Suppose we have a box with 4 numbered balls. 2 are white and 2 are black.

Random Experiment: Select one ball at random.

* $A$ = black ball is selected
* $B$ = even numbered ball is selected
* $C$ = number on the selected ball is greater than 2
* balls are denoted as: $\{(1,b),(2,b),(3,w),(4,w)\}$

$$
A = \{(1,b),(2,b)\}
$$
$$
B = \{(2,b),(4,w)\}$$
$$
$$
C = \{(3,w),(4,w)\}
$$

What is $P(A|B)$ and $P(A|C)$?

* $$P(A|B) = \frac{P(A\cap B)}{P(B)} = \frac{\frac{1}{4}}{\frac{1}{2}} = \frac{1}{2}$$
* $$P(A|C) = \frac{P(A\cap C)}{P(C)} = \frac{0}{\frac{1}{2}} = 0$$

Example 2: Suppose we have a box with 5 balls, 2 of which are black and 3 of which are white. Suppose we pick two balls without replacement. What is the probability that both balls are white?

$$
P(A|B) = \frac{P(A\cap B)}{P(B)}
$$

$$
P(A|B)P(B) = P(A\cap B)
$$

Therefore: 

$$
P(w_1\cap w_2) = P(w_2|w_1)P(w_1) = \frac{1}{2}\times \frac{3}{5} = \frac{3}{10}
$$

## Partition and Total Probability:

Let $B_1,B_2,...,B_n$ be mutually exclusive events whose union is $S$. Such a collection of events is called a `partition`. 

$$
P(A) = P(A|B_1)P(B_1) + P(A|B_2)P(B_2) + ... +  P(A|B_n)P(B_n)
$$

Proof: 

$$
A = A\cap S
$$
$$
= A\cap(B_1\cup B_2\cup ... \cup B_n)
$$
$$
= (A\cap B_1)\cup (A\cap B_2)\cup ... \cup (A\cap B_n)
$$

$$
B_1 \cap B_2 = \emptyset
$$
$$
(A\cap B_1) \cap (A\cap B_2) = \emptyset
$$

So we can use the third axiom of probability:

$$
P(A)=P(A\cap B_1)\cup P(A\cap B_2)\cup ... \cup P(A\cap B_n)
$$

So from the definition of a conditional probability:

$$ 
P(A\cap B_1) = P(A|B_1)P(B_1)
$$
$$
P(A\cap B_2) = P(A|B_2)P(B_2)
$$
$$
\vdots
$$
$$
P(A\cap B_2) =P(A|B_n)P(B_n)
$$

$$
\therefore \text{   } P(A)=\sum_{k=1}^nP(A|B_k)P(B_k)
$$

The statement above is the `Total Probability Law`.

So if we go back to the problem from before:

$$
P(w_2) = P(w_2|w_1)P(w_1) + P(w_2|b_1)P(b_1) $$ $$
= \frac{1}{2} \times \frac{3}{5} + \frac{3}{4} \times \frac{2}{5} = \frac{3}{5}
$$

## Bayes Rule

$$
P(B|A) = \frac{P(B\cap A)}{P(A)}
$$
$$
P(B\cap A) = P(A\cap B)=P(A|B)P(B)
$$
$$
=P(B|A)P(A)
$$

$$
P(B|A) = \frac{P(A|B)P(B)}{P(A)}
$$

Example: Binary Communication Channel:

We have an input $X$ and output $Y$.

$$
P(\text{output}=1|\text{input}=0)=\epsilon_1
P(\text{output}=0|\text{input}=1)=\epsilon_2
$$

In particular, if $\epsilon_1 = \epsilon_2$ this is known as a binary symmetric channel `BSC`.

* $X_k$ is the event that bit $k$ is transmitted
* $Y_k$ is the event that bit $k$ is received
* Assume bits are transmitted equally likely. $P(X_0) = P(X_1) = \frac{1}{2}$

Q1: What is the probability that bit 1 is received?

Q2: What is the probability that bit 1 was transmitted given that bit 1 is received?

1. $$P(Y_1) = P(Y_1|X_1)P(X_1) + P(Y_1| X_0)P(X_0) $$

$$P(X_1)= P(X_0) = \frac{1}{2} $$

$$P(Y_1|X_1) = 1 - \epsilon_2 $$

$$P(Y_1|X_0) = \epsilon_1 $$

$$P(Y_1) = \epsilon_1 \frac{1}{2} + (1-\epsilon_2)\frac{1}{2} $$

2. $$P(X_1|Y_1)= \frac{P(Y_1|X_1)P(X_1)}{P(Y_1)} $$

$$ = \frac{((1-\epsilon_2)\frac{1}{2})}{(1-\epsilon_2)\frac{1}{2}+\epsilon_1\frac{1}{2}} $$

## Independence

We define two events $A$ and $B$ as independent if $P(A\cap B) = P(A)\times P(B)$

Recall: $$P(A|B) = \frac{P(A\cap B)}{P(B)}$$

If $$A\perp \perp B$ then $$P(A|B) = \frac{P(A)\times P(B)}{P(B)} = P(A)$$

Likewise, if $A\perp \perp B$ then $P(A|B) = P(B)$

Q: Are two events that are mutually exclusive also independent? No.

$$
P(A|B) = \frac{P(A\cap B)}{P(B)} = \frac{P(\emptyset)}{P(B)}=0 \ne P(A)
$$
