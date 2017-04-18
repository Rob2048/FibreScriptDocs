.. _camera_hardware:

===============
Camera Hardware
===============

.. currentmodule:: picamera

This chapter provides an overview of how the camera works under various
conditions, as well as an introduction to the software interface that picamera
uses.

.. _operations:

Theory of Operation
===================

Many questions I receive regarding picamera are based on misunderstandings of
how the camera works. This chapter attempts to correct those misunderstandings
and gives the reader a basic description of the operation of the camera. The
chapter deliberately follows a `lie-to-children`_ model, presenting first a
technically inaccurate but useful model of the camera's operation, then
refining it closer to the truth later on.

Misconception #1
----------------

The Pi's camera module is basically a mobile phone camera module. Mobile phone
digital cameras differ from larger, more expensive, cameras (`DSLRs`_) in a
few respects. The most important of these, for understanding the Pi's camera,
is that many mobile cameras (including the Pi's camera module) use a `rolling
shutter`_ to capture images. When the camera needs to capture an image, it
reads out pixels from the sensor a row at a time rather than capturing all
pixel values at once.

In fact, the "global shutter" on DSLRs typically also reads out pixels a row at
a time. The major difference is that a DSLR will have a physical shutter that
covers the sensor.  Hence in a DSLR the procedure for capturing an image is to
open the shutter, letting the sensor "view" the scene, close the shutter, then
read out each line from the sensor.

The notion of "capturing an image" is thus a bit misleading as what we actually
mean is "reading each row from the sensor in turn and assembling them back into
an image".