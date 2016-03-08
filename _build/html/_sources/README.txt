Statistical Mechanics Notes
----------------------------

Just for my stat mech course. The requirement is to use LaTeX however I just think it might be better to use Sphinx to generate multiple formats with only one source.

.. image:: https://raw.github.com/GuokrUnion/GuokrBadge/master/cc/gs/cc_byncsa.flat.guokr.32.png
   :target: http://creativecommons.org/licenses/by-nc-sa/3.0/us/

This project is under `CC BY-NC-SA license <http://creativecommons.org/licenses/by-nc-sa/3.0/us/>`_ .

This project can be cited as 

.. image:: https://zenodo.org/badge/7726/emptymalei/StatisticalPhysics.svg   
   :target: http://dx.doi.org/10.5281/zenodo.13198



Thanks to Professor Kenkre for his excellent teaching.






------


Instructions From Original Theoretical Physcis Repo
---------------------------------------------------

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
