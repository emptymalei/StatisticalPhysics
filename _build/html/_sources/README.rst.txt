Statistical Mechanics Notes
----------------------------

The notes are online: `http://statisticalphysics.openmetric.org <http://statisticalphysics.openmetric.org>`_

Notes for my stat mech course. I used the sphinx configuration files and exts filese from `theoretical-physics <https://github.com/certik/theoretical-physics>`_ (I kept all the commits from the original author, even though I deleted all the contents).

This project is under `CC BY-NC-SA license <http://creativecommons.org/licenses/by-nc-sa/3.0/us/>`_ .

.. image:: https://raw.github.com/GuokrUnion/GuokrBadge/master/cc/gs/cc_byncsa.flat.guokr.32.png
   :target: http://creativecommons.org/licenses/by-nc-sa/3.0/us/


Thanks to Professor Kenkre for his excellent lectures.




------

------


Instructions From Original Theoretical Physcis Repo by Ondřej Čertík
------------------------------------------------------------------------------------------------------

This is an opensource book, available online at:

http://theoretical-physics.net/

All files in the repository are licensed under the MIT license. The source code
of the repository is available at:

http://github.com/certik/theoretical-physics

Build
-----

Install prerequisites::

    sudo apt-get install python-sphinx texlive-fonts-recommended texlive-latex-extra texlive-fonts-extra dvipng

To build the book, do::

    make web

This builds both html and pdf versions, that you can find in the _build
directory.

How to Push to Github
---------------------

First fetch the gh-pages branch and then use this script::

    ./copy-docs

and optionally push the gh-pages branch to github::

    git push github
