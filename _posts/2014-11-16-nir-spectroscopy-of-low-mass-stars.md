---
layout: post
title: "NIR spectroscopy of low mass stars - part 1"
description: "A closer look on NIR spectroscopy"
category: Astronomy
tags: [astronomy, m-dwarfs, spectroscopy, NIR]
---
{% include JB/setup %}

## Why M-dwarfs
Today I will give an introduction to my work on low mass stars, in particular
M-dwarfs. Why are M-dwarfs interesting at all? Well, for several reasons, here I
give the two biggest (in my opinion)

    1. About 70% of the stars in the Milky Way is M-dwarfs.
    2. Small rocky exoplanets are known to be prone to form around low mass stars.

So first of all, it is alway interesting to study something numerous
which is the case here. Second of all, astronomy is pushing the limits
for the hunt of the Earth's twin, i.e. an exoplanet with roughly same
size and mass as the Earth but also in the habitable zone. The habitable
zone is a zone to be found around a star, where temperature allow liquid
water to exist (0-100 degrees Celsius).

Another nice thing about M-dwarfs is that they are cool (because of their low
mass). This means that an exoplanet can be closer in its orbit and still be in
the habitable zone compared to the Earth. Therefore they require less time to
observe in order to find them. To comparison if we want to observe the Earth
from outer space with the transit method, we will need roughly three years of
observations. This gives us three transits which we say is the minimum to
identify a potential exoplanet.


## What is the problem anyway?
The problem with M-dwarfs is they are faint. This is because of their
cool temperature which is all related in one simple equation

![equation](http://www.sciweavers.org/tex2img.php?eq=L%20%3D%204%5Cpi%20R%5E2%20%5Csigma%20T_%7Beff%7D%5E4&bc=Black&fc=Gray&im=jpg&fs=12&ff=arev&edit=0)

Here `L` is the luminosity, `R` is the radius, and `T` is the effective
temperature. The rest are constants. Here we see that a low effective
temperature (the temperature at the surface) gives a low luminosity why
the M-dwarfs are difficult to observe.

Another issue with M-dwarfs is the formation of molecules in the
atmosphere. Molecules are more complicated than single atoms in terms
of spectroscopy (an probably many other terms as well). Molecules have
the nasty habit of depressing the continuum in the visible part of the
spectra. Determination of the continuum is crucial and non-trivial when
working with spectroscopy. However, this problem is smaller in the Near
InfraRed (NIR).


## Next step
The natural next step is to move the spectroscopic analysis to the NIR where
continuum depression is smaller. Another advantage of this region are due to
the fact, that M-dwarfs are very red. This means that most of their light is
actually emitted in the NIR/IR and therefore we can in principle observe for a
shorter time to reach the same signal-to-noise-ratio (SNR). A problem in the
NIR, is the instrumentation. Currently there is not many NIR spectrographs up
and running. Luckily some are planned to be up soon, so we can observe the most
abundant stars in the Universe (limited to our own galaxy).


## How does characterization work?
When characterising stars from spectroscopy, there are two main methods.

    1. The Synthesis method. Fitting the spectra with a model spectrum and read the parameters from the model.
    2. The Equivalent Width (EW) method. Here one measure the EW of chosen spectral lines and force fit these
 to find the parameters.

The latter is more a line-by-line analysis whereas the first method is more a
fit to a whole region.

The methods are more complicated than sketched, but my guess is, that
if you read this, you know what I am talking about already (otherwise
you should feel free to leave a comment down below, and I will try to
explain it in more detail).

For this project I use the second method, everything is done from
scratch! This means that the best spectral lines in a huge wavelength
region will be picked out more or less manually and tested. To pick the
lines, I use the Sun as a template since this is the star we know best,
and we have high-quality spectra in the NIR. Also, I want my method to
not only work for M-dwarfs but also for FGK-dwarfs. The reason for this
is, that I will start using the method on well known FGK-dwarfs and test
the validity of the linelist before moving to M-dwarfs. In this way I
am able to present a linelist that works consistently for FGK+M-dwarfs
which the community currently lacks.

## What is next
Currently I have a calibrated linelist for the Sun. I am preparing some data
for an F star from the CRIRES spectrograph. When the data is reduced, I will
measure EW of this star, and hopefully be able to refine the linelist and
determine good parameters compared to the literature.

A part 2 will follow of this post in the "near" future. The goal now is around
January/February. This would be after I publish the paper describing above -
hopefully :)

Stay tuned for more.
