PhotometricSuperflat
====================

PixInsight module to create a photometric superflat

This module reads a table produced by the AperturePhotometry script, fits a
polynomial surface (of degree up to 4) to the data and produces a photometric
superflat frame as well as a couple of plots showing the relative flux errors
in the calibration stars with and without the application of the flat. Here is
a screenshot showing it in use:

https://dl.dropboxusercontent.com/u/110230258/SuperflatScreenshot.png

The easiest way to test it out is with simulated data. To do this, generate a
fake image using the CatalogStarGenerator script, then modify this image with
some function using the PixelMath module. (It's obviously important that you
modify the image using some sort of multiplicative process and not an additive
process). Run the AperturePhotometry script on the simulated image to generate
a catalog. Then fire up the PhotometricSuperflat process and click on the
button to select the catalog (whose filename will end with _WCS.csv). Then
drag the process icon onto the image you have just photometered to generate the
Superflat and diagnostic plots.

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


License
-------

Copyright (c) 2014, Roberto G. Abraham All rights reserved.

Redistribution and use in source and binary forms, with or without modification, are permitted provided that the following conditions are met:

1. Redistributions of source code must retain the above copyright notice, this list of conditions and the following disclaimer.

2. Redistributions in binary form must reproduce the above copyright notice, this list of conditions and the following disclaimer in the documentation and/or other materials provided with the distribution.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT OWNER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.

The views and conclusions contained in the software and documentation are those of the authors and should not be interpreted as representing official policies, either expressed or implied, of the FreeBSD Project.
