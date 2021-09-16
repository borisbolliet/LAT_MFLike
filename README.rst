=============================
LAT Multifrequency Likelihood
=============================

An external likelihood using `cobaya <https://github.com/CobayaSampler/cobaya>`_.

.. image:: https://img.shields.io/github/workflow/status/simonsobs/LAT_MFLike/Unit%20test%20for%20mflike/feature-github-actions
   :target: https://github.com/simonsobs/LAT_MFLike/actions

.. image:: https://mybinder.org/badge_logo.svg
   :target: https://mybinder.org/v2/gh/simonsobs/LAT_MFLike/master?filepath=notebooks%2Fmflike_tutorial.ipynb


Installing the code
-------------------

You first need to clone this repository to some location

.. code:: shell

    $ git clone https://github.com/simonsobs/LAT_MFLike.git /where/to/clone

Then you can install the ``mflike`` likelihood and its dependencies *via*

.. code:: shell

    $ pip install -e /where/to/clone

The ``-e`` option allow the developer to make changes within the ``mflike`` directory without having
to reinstall at every changes. If you plan to just use the likelihood and do not develop it, you can
remove the ``-e`` option.

Installing LAT likelihood data
------------------------------

Preliminary simulated data can be found at `NERSC
<https://portal.nersc.gov/cfs/sobs/users/MFLike_data>`_. You can download them by yourself but you
can also use the ``cobaya-install`` binary and let it do the installation job. For instance, if you
do the next command

.. code:: shell

    $ cobaya-install /where/to/clone/examples/mflike_example.yaml -p /where/to/put/packages

data and code such as `CAMB <https://github.com/cmbant/CAMB>`_ will be downloaded and installed
within the ``/where/to/put/packages`` directory. For more details, you can have a look to ``cobaya``
`documentation <https://cobaya.readthedocs.io/en/latest/installation_cosmo.html>`_.

Running/testing the code
------------------------

You can test the ``mflike`` likelihood by doing

.. code:: shell

    $ cobaya-run /where/to/clone/examples/mflike_example.yaml -p /where/to/put/packages

which should run a MCMC sampler for the simulation n°44 (*i.e.* ``data_sacc_00044.fits`` in the
``mflike_example.yaml`` file) using the combination of TT, TE and EE spectra (*i.e.*
``polarizations: ['TT', 'TE', 'ET', 'EE']``). The results will be stored in the ``chains/mcmc``
directory.

Contributors
------------

.. image:: https://contrib.rocks/image?repo=simonsobs/LAT_MFLike
   :target: https://github.com/simonsobs/LAT_MFLike/graphs/contributors
