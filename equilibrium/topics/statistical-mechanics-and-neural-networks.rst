Statistical Mechanics and Artificial Neural Networks
=====================================================

.. warning::

   This article is just food for thought. No guarantee whatsoever.

   This article assumes background knowledge about the basics of artificial neural networks.

   I wrote a brief `crash course <https://datumorphism.github.io/wiki/artificial-neural-networks/physicists-crash-course-neural-network/>`_ on artificial neural networks if it helps.


One of the reason that statistical physics works is that we have common properties in the building blocks, i.e., the particles in the physical system. To construct a macroscopic property of the system, we "encapsulate" the building blocks and expose a few relevant properties.

What is even more exciting is that we could even ignore the correlations between the building blocks if they are "sparsely distributed", i.e., more or less independent and identical. This makes the statistics easy to calculate.

.. note::
   "Sparsely distributed" doesn't indicate the spatial distributions. It shows the interactions.

For systems with more interactions between the building blocks, we need more work to find suitable distribution for the probabilities of the states of the building blocks. In general, we describe the flow of the states in phase space using the Liouville equation.

In artificial neural networks, the neurons are our building blocks. We also encapsulate them so that we only expose a few metrics and parameters. That being said, we also have a phase space for the neurons in artificial neural networks that we can use to describe a general flow of the states in the phase space once the network during training.

In essence, this becomes a highly non-equilibrium problem. There are a few interesting questions to be investigated.

1. Do the neurons have strong interactions? The interactions should come from the training algorithms such as backpropagation.
2. Can we find a law for the phase space distribution and motion probabilities?
3. Do the equilibrium state follow the Liouville equation? It is hard to validate this since the equilibrium state of the neural network doesn't change that much.

Also, what do we gain from this investigation?


References
---------------------


1. `A Physicist's Crash Course on Artificial Neural Network <https://datumorphism.github.io/wiki/artificial-neural-networks/physicists-crash-course-neural-network/>`_