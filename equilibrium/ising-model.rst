Ising Model
====================

Ising model is a simple and powerful model in magnetism. Given its simplicity, Ising model has been expanding to other fields of science.

As an example, we use the Ising model to describe ferromagnetic materials. It's Hamiltonian is as simple as

.. math::
   \mathscr H = - J \sum_{\langle i,j \rangle} \sigma_i \sigma_j - \mu B \sum_{i} \sigma_i.

where :math:`- J \sum_{\langle i,j \rangle} \sigma_i \sigma_j` is energy of the magnetic moment self-interactions, and the second term :math:`- \mu B \sum_{i} \sigma_i` is the energy of the magnet moments and the external field :math:`B`.

With the above Hamiltonian, we can write down the partition function from which we derive all the thermodynamic observables, in principle. For example, we are quite interested in solving the order parameters such as the average spin :math:`\langle s \rangle` so we could infer from this the phase transitions.

Ising model can be analytically and exactly solved in 1D easily and in 2D with some tricks. However, it becomes hard to solve exactly in 3D. We turn to approximations and numerical methods for help. One example of approximations is the :ref:`mean-field-theory`, while the Monte Carlo method is the famous numerical method.

Phase Transitions
----------------------

Ising model is simple to solve numerically yet it provides insights in terms of many thermodynamical phenomona. Phase transitions in Ising model is one of the examples. During the phase transition, we could explicitly see the correlation length of the spins becomes infinily, or simply large in finite systems. Many techniques have been used to investigate such behaviors such as scaling, numerical methods, etc.


Metropolis Algorithm
----------------------------


Metropolis algorithm is a Monte Carlo method for sampling. We will calculate the energy :math:`\langle E \rangle` and magnetization :math:`\langle M \rangle` of the equilibrium Ising model. The specific heat and magnetic susceptibility can be calculated using the energy and magnetization.


To demonstrate the algorithm, we use a 2D N by N lattice of magnetic spins.

.. figure:: images/metropolis-algorithm-flowchart.png
   :alt: Metropolis algorithm
   :align: center

   Metropolis algorithm

.. admonition:: Flowchart Code
   :class: toggle

   `Here <https://mermaidjs.github.io/mermaid-live-editor/#/edit/eyJjb2RlIjoiZ3JhcGggVERcbkFbSW5pdGlhbGl6ZSBsYXR0aWNlIHNwaW5zIHJhbmRvbWx5XSAtLT4gQihyYW5kb21seSBmbGlwIGEgc3BpbilcbkIgLS0-IEN7XCJJcyDiiIZFIDwgMCA8YnI-IG9yIDxicj4gZXhwKC3iiIZFL2JldGEpID4gcmFuZG9tIG51bWJlciBbMCwxXVwiIH1cbkMgLS0-fFRydWV8IEQoQWNjZXB0IGZsaXApXG5DIC0tPnxGYWxzZXwgRihSZWplY3QgZmxpcClcbkQgLS0-IEp7XCJJcyBlcXVpbGlicml1bVwifVxuRiAtLT4gSntcIklzIGVxdWlsaWJyaXVtXCJ9XG5KIC0tPiB8RmFsc2V8IEJcbkogLS0-IHxUcnVlfCBLW1wiQ29sbGVjdGVkIGRhdGEgYW5kIGNhbGN1bGF0ZSBvYnNlcnZhYmxlc1wiXVxuXG4iLCJtZXJtYWlkIjp7InRoZW1lIjoibmV1dHJhbCJ9fQ>`_ `is <https://mermaidjs.github.io/mermaid-live-editor/#/view/eyJjb2RlIjoiZ3JhcGggVERcbkFbSW5pdGlhbGl6ZSBsYXR0aWNlIHNwaW5zIHJhbmRvbWx5XSAtLT4gQihyYW5kb21seSBmbGlwIGEgc3BpbilcbkIgLS0-IEN7XCJJcyDiiIZFIDwgMCA8YnI-IG9yIDxicj4gZXhwKC3iiIZFL2JldGEpID4gcmFuZG9tIG51bWJlciBbMCwxXVwiIH1cbkMgLS0-fFRydWV8IEQoQWNjZXB0IGZsaXApXG5DIC0tPnxGYWxzZXwgRihSZWplY3QgZmxpcClcbkQgLS0-IEp7XCJJcyBlcXVpbGlicml1bVwifVxuRiAtLT4gSntcIklzIGVxdWlsaWJyaXVtXCJ9XG5KIC0tPiB8RmFsc2V8IEJcbkogLS0-IHxUcnVlfCBLW1wiQ29sbGVjdGVkIGRhdGEgYW5kIGNhbGN1bGF0ZSBvYnNlcnZhYmxlc1wiXVxuXG4iLCJtZXJtYWlkIjp7InRoZW1lIjoibmV1dHJhbCJ9fQ>`_ the mermainjs link.

   .. code-block:: text

      graph TD
      A[Initialize lattice spins randomly] --> B(randomly flip a spin)
      B --> C{"Is ∆E < 0 <br> or <br> exp(-∆E/beta) > random number [0,1]" }
      C -->|True| D(Accept flip)
      C -->|False| F(Reject flip)
      D --> J{"Is equilibrium"}
      F --> J{"Is equilibrium"}
      J --> |False| B
      J --> |True| K["Collected data and calculate observables"]



`This GitHub repository <https://github.com/emptymalei/ising-model>`_ is my working example of this algorithm for Ising model.




Refs & Notes
---------------

1. Reichl, L., A Modern Course in Statistical Physics.
2. `Murthy, K. P. N. (2001). An Introduction to Monte Carlo Simulation of Statistical physics Problem. <http://arxiv.org/abs/cond-mat/0104167>`_