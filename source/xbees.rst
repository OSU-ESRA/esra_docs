XBees
=====

XBees are wireless transceivers used as a transparent serial bus to communicate
with the vehicles.

Configuration
-------------

Use the `XBee command reference`_ to determine how to properly set the following
settings:

DH, DL
   These specify the destination address, and should be set to the SH and SL
   values of the paired XBee.

BD
   This is the baud rate for the serial communication. Set to ``5`` (38400 baud).

.. _`XBee command reference`: http://examples.digi.com/wp-content/uploads/2012/07/XBee_ZB_ZigBee_AT_Commands.pdf
