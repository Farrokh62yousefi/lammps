.. index:: angle_style harmonic

angle_style harmonic command
============================

angle_style harmonic/intel command
==================================

angle_style harmonic/kk command
===============================

angle_style harmonic/omp command
================================

Syntax
""""""

.. code-block:: LAMMPS

   angle_style harmonic

Examples
""""""""

.. code-block:: LAMMPS

   angle_style harmonic
   angle_coeff 1 300.0 107.0

Description
"""""""""""

The *harmonic* angle style uses the potential

.. math::

   E = K (\theta - \theta_0)^2

where :math:`\theta_0` is the equilibrium value of the angle, and :math:`K` is a
prefactor.  Note that the usual 1/2 factor is included in :math:`K`.

The following coefficients must be defined for each angle type via the
:doc:`angle_coeff <angle_coeff>` command as in the example above, or in
the data file or restart files read by the :doc:`read_data <read_data>`
or :doc:`read_restart <read_restart>` commands:

* :math:`K` (energy/radian\^2)
* :math:`\theta_0` (degrees)

:math:`\theta_0` is specified in degrees, but LAMMPS converts it to radians
internally; hence the units of :math:`K` are in energy/radian\^2.

----------

Styles with a *gpu*\ , *intel*\ , *kk*\ , *omp*\ , or *opt* suffix are
functionally the same as the corresponding style without the suffix.
They have been optimized to run faster, depending on your available
hardware, as discussed on the :doc:`Speed packages <Speed_packages>` doc
page.  The accelerated styles take the same arguments and should
produce the same results, except for round-off and precision issues.

These accelerated styles are part of the GPU, USER-INTEL, KOKKOS,
USER-OMP and OPT packages, respectively.  They are only enabled if
LAMMPS was built with those packages.  See the :doc:`Build package <Build_package>` doc page for more info.

You can specify the accelerated styles explicitly in your input script
by including their suffix, or you can use the :doc:`-suffix command-line switch <Run_options>` when you invoke LAMMPS, or you can use the
:doc:`suffix <suffix>` command in your input script.

See the :doc:`Speed packages <Speed_packages>` doc page for more
instructions on how to use the accelerated styles effectively.

----------

Restrictions
""""""""""""

This angle style can only be used if LAMMPS was built with the
MOLECULE package.  See the :doc:`Build package <Build_package>` doc
page for more info.

Related commands
""""""""""""""""

:doc:`angle_coeff <angle_coeff>`

**Default:** none
