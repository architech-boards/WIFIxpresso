.. index:: Factory Reset

.. _factoryreset:

Factory Reset
=============

by terminal
-----------

.. warning:: For using this mode you need a **UART interface (3,3V level only)** to connect WIFIxpresso to your pc. **This interface is not provided**.

It can be possible reset to factory defaults module **RN-131C** through the :ref:`passthrough` with the following commands:

1. Place the mode **RN-131C** module in command mode

::

 $$$

2. Reset the module to factory default conditions.

::

 factory R

3. Reboot the device.

::

 reboot


by hardware
-----------

.. image:: _static/IMG13.jpg

To reset to the factory settings the **RN-131C** module means hardware you need to follow the following steps:

1. insert the jumpers **J1** and **J2**

2. start the demo

3. take off and put the jumper **J2** until the **LED3**, **LED5** do not flash.

