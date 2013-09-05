Update RN-131C firmware
=======================

.. index:: FTP Update

FTP Update
----------

.. important::

 1. To proceed you need a **UART interface (3,3V level only)** to connect WIFIxpresso to your pc. **This interface is not provided**.
 2. Requires **Wi-Fi network** with **internet access**!

1. Starting from :ref:`passthrough`, type following commands to update **RN-131C** firmware:

2. Restore module to factory defaults, type these commands:

::

 $$$
 factory R
 save
 reboot

3. Associate to Internet-Connected Network your network

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

5. After downloading new firmware it is recommended restore module to factory defaults one more time before using it

::

 $$$ 
 factory R
 save
 reboot

