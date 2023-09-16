List of Lemmas idk if there will be proofs probably only for the non-trivial ones {#list-of-lemmas-idk-if-there-will-be-proofs-probably-only-for-the-non-trivial-ones .unnumbered}
=================================================================================

Definition 1.1 {#definition-1.1 .unnumbered}
--------------

We define the Fibonacci sequence as the sequence where $$f_0 = 0$$,
$$f_1 = 1$$ and $$f_n = f_{n-1} + f_{n-2}$ for all $n \in \mathbb{Z}$$. This
isn't really a sequence since we've extended the domain to the integers
but oh well.

Lemma 1.2 {#lemma-1.2 .unnumbered}
---------

$f_{a+b} - f_a = \sum_{i = -1}^{b-2} f_i$\
Pf: This is obviously true by induction.

Lemma 1.3 {#lemma-1.3 .unnumbered}
---------

For $a \in Z$, $f_{a+b} = f_{b+1}f_{a} + f_{b}f_{a-1}$.\
Pf: We proceed by induction. If $b=1$ or $b=2$ then this is obvious.
Then by the inductive hypothesis we have
$$f_{a+b} = f_{a+b-1} + f_{a+b-2} =  f_{b}f_{a} + f_{b-1}f_{a-1} +  f_{b-1}f_{a} + f_{b-2}f_{a-1} =  f_{b}f_{a-1} + f_{b+1}f_{a}$$
So we have the desired result.

Notation 1.4 {#notation-1.4 .unnumbered}
------------

We denote the $n$th fib number mod $m$ as $f_n^m$.

Lemma 1.5 {#lemma-1.5 .unnumbered}
---------

For all $m \in \mathbb{N}$ there exists a $b \in \mathbb{N}$ st.
$f^m_a = f^m_{a+bz}$ for all $a,z \in Z$\
Pf outline: by pigeonhole we must have after some finite amount a pair
of consecutive numbers that repeat since the next term is uniquely
defined by two numbers it must then repeat. Idea for this comes from a
proof of a problem in the book \"Putnam and Beyond\".

Definition 1.6 {#definition-1.6 .unnumbered}
--------------

We define $p(m)$, the period mod $m$ as the smallest $b \in Z$
satisfying $f^m_a = f^m_{a+bz}$ for all $a,z \in Z$, which always exists
as a result of Lemma 1.5.

Definition 1.7 {#definition-1.7 .unnumbered}
--------------

We define $sp(m)$, the semi-period mod $m$ as the smallest $b \in Z$
satisfying $f^m_a = -f^m_{a+bz}$ for all $a,z \in Z$ if this value
exists.

Definition 1.6 {#definition-1.6-1 .unnumbered}
--------------

We define $mp(m)$, the min-period mod $m$ as the smallest $b \in N$
satisfying $f^m_{b} = 0$ which always exists as the sequence is periodic
mod $m$ and $f_0 = 0$.

Lemma 1.7 {#lemma-1.7 .unnumbered}
---------

$$\sum_{i = a}^{a+p(m)-1}f_{a}^m = 0$$ Pf:
$$\sum_{i = a}^{a+p(m)-1}f_{a}^m = \sum_{i = a}^{a+p(m)-1}f_{a} \quad \text{mod} \quad m = f_{a+1 + p(m)} - f_{a+1} \quad \text{mod} \quad m = 0$$

Lemma 1.8 {#lemma-1.8 .unnumbered}
---------

If $m$ is prime then $f^m_a = 0$ iff $mp(m) | a$.\
Pf: First we will show the reverse direction. Let $a = b*mp(m)$ for some
$b \in \mathbb{N}$. Proceed by induction on $b$. If $b = 1$ then clearly
$f^m_a = f^m_{mp(m)} = 0$. Then if the statement is true for $k<n$ we
have that
$f^m_a = f^m_{mp(m)*(n-1) + mp(m)} = f^m_{mp(m)*(n-1)}f^m_{mp(m)+1} + f^m_{mp(m)}f^m_{mp(m)*(n-1)-1} = 0$.
So we have the desired result.

Now we show the forward direction using the reverse direction. Let $a$
be st. $a$ is not divisible by $mp(m)$. Then $a = b * mp(m) + c$ for
some $b,c \in \mathbb{N}$. Notice $b$ is never $0$ since if $b = 0$ then
we have a contradiction since $a < mp(m)$ and $f^m_a = 0$. By the
forward direction $f_{b*mp(m)}^m = 0$. Then by lemma 1.3 we have that
$f^m_a = f_{b*mp(m) + c}^m = f_{b*mp(m)}^mf_{c+1}^m + f_{c}^mf_{b*mp(m)-1}^m = 0 + f_{c}^mf_{b*mp(m)-1}^m \neq 0$.
This is because $f_{b*mp(m)-1}^m \neq 0$ since otherwise the entire
sequence is $0$ which is not possible and because $f_{c}^m \neq 0$ since
$c < mp(m)$ so if $f_{c}^m = 0$ we have a contradiction. Then since $m$
is prime two non zero values cannot multiply to $0$ so we are done.

Lemma 1.10 {#lemma-1.10 .unnumbered}
----------

For all $m \in \mathbb{N}$ $f^m_a = 0$ if $mp(m) | a$.\
Pf: Same proof as the reverse direction of Lemma 1.8. Let $a = b*mp(m)$
for some $b \in \mathbb{N}$. Proceed by induction on $b$. If $b = 1$
then clearly $f^m_a = f^m_{mp(m)} = 0$. Then if the statement is true
for $k<n$ we have that
$f^m_a = f^m_{mp(m)*(n-1) + mp(m)} = f^m_{mp(m)*(n-1)}f^m_{mp(m)+1} + f^m_{mp(m)}f^m_{mp(m)*(n-1)-1} = 0$.
So we have the desired result.

Definition 1.11 {#definition-1.11 .unnumbered}
---------------

We define the scaling factor of $m$ or $s(m)$ to be the value st.
$s(m)*f^m_{a} = f^m_{mp(m)+a}$ for all $a \in N$.

Lemma 1.11 {#lemma-1.11 .unnumbered}
----------

Scaling factor is well defined and
$s(m) = f^m_{mp(m)+1} = f^m_{mp(m)-1}$.\
Pf:\
By lemma $1.10$ we have that $f^m_{mp(m)} = 0$ so
$f^m_{mp(m)+1} = f^m_{mp(m)} + f^m_{mp(m)-1} = f^m_{mp(m)-1}$ and:
$$f^m_{mp(m)+a} = f^m_{mp(m)+1}f^m_{a} + f^m_{mp(m)}f^m_{a-1} = f^m_{mp(m)+1}f^m_{a}$$
Therefore the scaling factor $s(m) = f^m_{mp(m)+1} = f^m_{mp(m)-1}$.

Theorem 1.12 {#theorem-1.12 .unnumbered}
------------

For all $m \in \mathbb{N}$ $f^m_a = 0$ iff $mp(m) | a$.\
Pf: The reverse direction is just Lemma 1.9.

Now we show the forward direction. Assume there is a set $S$ st.
$a \in S$ implies $a$ is not divisible by $mp(m)$ and $f^m_{a} = 0$. By
the well ordering principle $S$ has a minimum value let this be $a$.
Then $a = b * mp(m) + c$ for some $b,c \in \mathbb{N}$. Notice $b$ is
never $0$ since if $b = 0$ then we have a contradiction since
$a < mp(m)$ and $f^m_a = 0$. Additionally, if $mp(m) = p(m)$ then we
immediately have that $f^m_{a-mp(m)} = f^m_{a-p(m)} = f^m_a = 0$ so
$a-mp(m) \in S$ which is a contradiction since $a$ is the smallest
element in $S$. Therefore $p(m) > mp(m)$. Then let $x$ be st.
$f^m_{xp(m)} < f^m_{a} < f^m_{(x+1)p(m)}$. Let $y$ be st.
$f^m_{a+ymp(m)} > f^m_{(x+1)p(m)}$. By definition 1.11
$f^m_{a+ymp(m)} = s(m)^yf^m_{a} = 0$

This is the trick where you look at the thing beside the 0 but its not
very useful here. possibly useful nowhere. Then we have that
$f^m_{a-1} = s(m)f^m_{a-mp(m)-1}$ and $f^m_{a+1} = s(m)f^m_{a-mp(m)+1}$.
We also have that $f^m_{a-1} = f^m_{a-1} + f^m_a = f^m_{a+1}$ so
$s(m)f^m_{a-mp(m)-1} = s(m)f^m_{a-mp(m)+1}$

Theorem 1.unkown for now {#theorem-1.unkown-for-now .unnumbered}
------------------------

Let $n = ab$ where $a,b \in N$ and $gcd(a,b) = 1$. Then
$mp(n) = lcm(mp(a), mp(b))$.\
Pf: First we show that $f^n_{lcm(mp(a), mp(b))} = 0$. By Lemma 1.8.5
since $mp(a) | lcm(mp(a), mp(b))$ we have that
$f^a_{lcm(mp(a), mp(b))} = 0$. Similarly, $f^b_{lcm(mp(a), mp(b))} = 0$.
This means that $a | f_{lcm(mp(a), mp(b))}$ and $b |lcm(mp(a), mp(b))$.
Since $a$ and $b$ are coprime this means that
$ab = n | f_{lcm(mp(a), mp(b))}$. Therefore
$f^n_{lcm(mp(a), mp(b))} = 0$. It remains to be shown that there is no
$x < lcm(mp(a), mp(b))$ with $x \in \mathbb{N}$ st.
$f^n_{lcm(mp(a), mp(b))} = 0$. If $f^n_{x} = 0$ then $f^a_{x} = 0$ and
$f^b_{x} = 0$.
