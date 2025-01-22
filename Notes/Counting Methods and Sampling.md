# Counting Methods, Sampling with/without Replacement and with/without Ordering

$$
P(\text{outcome}) = \frac{1}{\text{number of outcomes}}
$$

Example: Suppose we have 4 equally likely outcomes

$$
P(\text{outcome}) = \frac{1}{4} = 0.25
$$

## Sampling with Replacemennt and with Ordering

Choose $k$ objects out of $n$ objects such that:

* when an object is selected, its value in the ordered list is noted.
* this object is returned to the list and can be re-used.

| Chosen | Number of Choices |
| --- | --- |
| 1st | $n$ |
| 2nd | $n$ |
| 3rd | $n$ |
| $\vdots$  | $\vdots$ |
| kth | $n$ |

Altogether, the number of outcomes that can be chosen from $n$ objects when picked $k$ times is:

$$
n \times n \times n \times ... \times n = n^k
$$

Example: How many ways can we answer a 10-questoin multiple choice test where each question has 4 possible answers.

For each question it there a 4 possible choices, so we get: $4 \times 4 \times ... \times 4 = 4^{10}$ total ways to answer the test. 

What is the probability of answering the test perfectly by random guessing?

$$
P = \frac{1}{4^{10}}
$$

What is the probability of getting 9 out of 10 answers correct by random guessing?

$$
P = \frac{10 \times 3}{4^{10}}
$$

* the 10 in the numerator is from the selection of any question we can get wrong
* the 3 comes the choice in how many ways we can get that selected question wrong
* the total number of outcomes remains the same, so the denominator remains the same

Note: the probability of getting 8 out of 10 correct can be calculated by:

$$
P = \frac{{10\choose 2}\times 3 \times 3}{4^{10}}
$$

* there are 10 choose 2 ways to select the questions that we get incorrect
* there are 3 ways to get one question wrong, with 2 questions, so we have the two 3's
* there are $4^{10}$ total outcomes.

Example: Suppose the box contains 5 balls, numbered 1 through 5. Pick 2 balls with replacement and order.

1. How many selections are possible?

By listing the whole sample space, we get:

$$
S = \{(1,1), (1,2), (1,3), (1,4), (1,5),
$$
$$
(2,1), (2,2), (2,3), (2,4), (2,5),
$$
$$
(3,1), (3,2), (3,3), (3,4), (3,5),
$$
$$
(4,1), (4,2), (4,3), (4,4), (4,5),
$$
$$
(5,1), (5,2), (5,3), (5,4), (5,5)\}
$$

There are 25 total outcomes.

2. What is the probability of picking the same ball twice? 

If we take a look at the diagonal of the sample space, we know that 

$$
P = \frac{5}{25} = \frac{1}{5}
$$

3. What is the probability of picking balls with adjacent numbers?

If balls 1 and 5 are picked first, the number of adjacent balls is equal to 1. When we look at balls, 2-4, the number of adjacent balls that can be picked is 2.
$$
P = \frac{1 + 1 + 2 * 3}{25} = \frac {8}{25}
$$

## Sampling without Replacement and Ordering

Choose $k$ numbered objects out of $n$ available objects. Once an object is selected, it is removed from further consideration.

| Chosen | Number of Choices |
| --- | --- |
| 1st | $n$ |
| 2nd | $n-1$ |
| 3rd | $n-2$ |
| $\vdots$  | $\vdots$ |
| kth | $n-k+1$ |

The total number of ways we can choose $k$ objects from $n$ objects is:

$$
n(n-1)(n-2)...(n-k+1)
$$

Example: Lets revisit the example above with 5 numbered balls, but now we sample without replacement.

1. How many selections are possible?

By listing the whole sample space, we get:

$$
S = \{(1,2), (1,3), (1,4), (1,5),
$$
$$
(2,1), (2,3), (2,4), (2,5),
$$
$$
(3,1), (3,2), (3,4), (3,5),
$$
$$
(4,1), (4,2), (4,3), (4,5),
$$
$$
(5,1), (5,2), (5,3), (5,4)\}
$$

There are 20 total outcomes.

2. What is the probability of picking the same ball twice? 

$$
P = 0
$$

3. What is the probability of picking balls with adjacent numbers?

If balls 1 and 5 are picked first, the number of adjacent balls is equal to 1. When we look at balls, 2-4, the number of adjacent balls that can be picked is 2.
$$
P = \frac{1 + 1 + 2 * 3}{20} = \frac {8}{20}
$$

For the special case of $k = n$, the number of total choices are:

$$
n(n-1)(n-2)...1 = n!
$$

Suppose we have a set $\{1,2,3\}$. How many ordered triples are there?

$$
3 \times 2 \times 1 = 3! = 6
$$

Back to the numbered balls example. What is the probability if the 5 balls are taken out one at a time that they are taken in ascending order? The balls are not replaced.

$$
P = \frac{1}{5\times 4\times 3\times 2\times 1} = \frac{1}{5!}
$$

## Sampling without Ordering and without Replacement

Suppose we have $n$ objects to choose from. When we draw $k$ objects one at a time from $n$ objects, we collectively set them aside and we inspect this collection as a whole.

$$
{n\choose k} = \frac{n(n-1)...(n-k+1)}{k!} = \frac{n!}{k!(n-k)!}
$$
$$
n(n-1)...(n-k+1) = \frac{n!}{(n-k)!}
$$

Example: Suppose we have a box with 5 balls numbered 1-5. What is the probability that when we pick 2 balls together, their sum is equal to 5?

$$
S = \{\{1,2\}, \{1,3\}, \{1,4\}, \{1,5\},
$$
$$
\{2,3\},\{2,4\},\{2,5\},
$$
$$
\{3,4\},\{3,5\},
$$
$$
\{4,5\}\}
$$

The total number of outcomes $|S| = 10$. We can also derive this by doing:

$$
{5\choose 2} = \frac{5!}{2!(5-2)!} = 10
$$

Probability that their sum is equal to 5 is: 

$$
P = \frac{2}{10} = \frac{1}{5}
$$ 

### Sampling with Replacement and without Ordering

The idea is to keep track of how many times each object was selected.

Example: Suppose we have 4 distinct objects. Pick them 5 times with replacement and without ordering.

| object1 | object2| object3 | object4|
| --- | --- | --- | --- |
| XX | | XX | X |
| XXXX | | X ||

In the table above, there are two examples of how we can pick the 4 objects.

Additionally we can use the following notation to display this type of sampling:

`_ _ | | _ _ | _`

We have 5 objects and 3 seperators that divides the 4 objects into groups. Thus we have 8 total black spaces that can either be taken by a seperator or a picked item.

In how many ways can we choose 3 positions of 8 possible positions?

$$
{8\choose 3} = \frac{8!}{3!5!}
$$

Now for the general case:

* $n$ objects picked $k$ times. The number of seperators will always be $n-1$. 

$$
{k+n-1\choose n-1} = {k+n-1\choose k}
$$

* How does choosing $n-1$ and choosing $k$ result in the same number of outcomes?
$$
{10\choose 3} = {10\choose 7}
$$
