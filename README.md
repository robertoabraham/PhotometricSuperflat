PhotometricSuperflat
====================

PixInsight module to create a photometric superflat


Notes on modifying the source code
----------------------------------

I find the trickiest part of creating PixInsight modules is handling
parameters. When you add a new parameter you need to add appropriate code in
these four files:

- PhotometricSuperflatParameters

- PhotometricSuperflatInterface

- PhotometricSuperflatInstance

- PhotometricSuperflatProcess  [Note: instantiate the process parameters in the
  constructor or you will get a segfault]
