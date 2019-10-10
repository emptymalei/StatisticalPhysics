Statistical Mechanics and Artificial Neural Networks
=====================================================

.. warning::

   This article is just food for thought. No guarantee whatsoever.

   This article assumes the background knowledge about basics of artificial neural networks.

   I have wrote a brief `crash course <https://datumorphism.com/wiki/artificial-neural-networks/physicists-crash-course-neural-network/>`_ on artificial neural networks if it helps.


One of the reason that statistical physics works is that we have common properties in the building blocks, i.e., the particles in the physical system. To construct a macroscopic property of the system, we "encapsulate" the building blocks and only expose a few relevant properties.

What is even more exciting is that we could even ignore the correlations between the building blocks if they are "sparsely distributed". This makes the statistics easy to calculate.

.. note::
   "Sparsely distributed" doesn't really indicate the spatial distributions. It indicates the interactions.

For systems with more interactions between the building blocks, we need more work to find a suitable distribution for the probabilities of the states of the building blocks. In general, we describe the flow of the states in phase space using Liouville equation.

In artificial neural networks, the neurons are our building blocks. We also encapsulate them so that we only expose a few metrics and parameters. The details of the neurons will be responsible for the training process. Presumbly, we don't care about the details of the neurons once the network has been trained.

That being said, we also have a phase space for the neurons in artificial neural networks that we can use to describe a general flow of the states in the phase space once the network has reached equalibrium.





References
---------------------


1. `A Physicist's Crash Course on Artificial Neural Network <https://datumorphism.com/wiki/artificial-neural-networks/physicists-crash-course-neural-network/>`_