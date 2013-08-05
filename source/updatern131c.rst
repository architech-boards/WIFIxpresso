Update RN-131C firmware
=======================

.. index:: FTP Update

FTP Update
----------

.. important:: Requires internet access!

1. Use :ref:`passthrough`

2. Restore module to factory defaults, type these commands:

::

 $$$
 factory R
 save
 reboot

3. Associate to Internet-Connected Network

::

 $$$
 scan
 set wlan ssid <insert here your ssid>
 set wlan pass <insert here your password>
 save
 reboot

4. Update firmware and verify the version number

::

 $$$
 ftp update
 ver
 reboot
 $$$
 ver

5. After downloading new firmware it is recommended restore module to factory defaults before using it

::

 $$$ 
 factory R
 save
 reboot

