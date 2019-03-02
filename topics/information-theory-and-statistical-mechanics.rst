Information Theory and Statistical Mechanics
===============================================

.. admonition:: Jaynes, E. T. (1957)
   :class: important
   
   Jaynes, E. T. (1957) Information Theory and Statistical Mechanics. Physical Review, 106(4), 620–630. https://doi.org/10.1103/PhysRev.106.620


Line of Reasoning
-------------------

Jaynes pointed out in this paper that we are solving an insufficient reason problem. What we could measure is some macroscopic quantity, from which we derive other macroscopic quantities. That being said, we know a system with a lot of possible microscopic states, :math:`\{ s_i \}` while the probabilities of each microscopic state :math:`\{p_i \}` is not know at all. We also know a macroscopic quantity :math:`\langle f(s_i) \rangle` which is defined as

.. math::
   \langle f \rangle = \sum_i p_i f(s_i).

The question that Jaynes asked was the following.

**How are we supposed to find another macroscopic quantities that also depends on the microscopic state of the system?** Say :math:`g(s_i)`.

It is a quite interesting question for stat mech. In my opinion, it can be generalized. To visualize this problem, we know think of this landscape of the states. Instead of using the state as the dimensions, we use the probabilities as the dimensions since they are unknown. In the end, we have a coordinate system with each dimension as the value of the probabilities :math:`\{p_i\}` and the one dimension for the value of :math:`\langle g \rangle (p_i)` which depends on :math:`\{p_i\}`. Now we constructed a landscape of :math:`\langle g \rangle (p_i)`. The question is, how do our universe arrange the landscape? Where are we in this landscape if we are at equilibrium?


In Jaynes' paper, he mentioned several crucial problems.

1. Do we need to find the exact location of our system? No.
2. How to calculate another macroscopic quantity based on one observed macroscopic quantity and the conservation of probability density? Using max entropy principle.
3. Why max entropy from the information point of view?
4. Why is the result actually predicting measurements even the theory is purely objective?
5. With the generality of the formalism, what else can we do with it to improve our statistical mechanics power?