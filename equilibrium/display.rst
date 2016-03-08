
.. code:: python

    %pylab inline
    from pylab import *

.. parsed-literal::

    Populating the interactive namespace from numpy and matplotlib


.. code:: python

    x=linspace(0,10,100)
    y=tanh(x)
.. code:: python

    figure()
    plot(x, y, 'r')
    xlabel('External Magnetic Field')
    ylabel('M')
    title('Tanh theory')
    show();


.. image:: display_files/display_2_0.png

