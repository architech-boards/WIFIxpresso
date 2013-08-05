.. index:: Pass-Through mode

.. _passthrough:

Pass-Through Mode
=================

The demo can operate in **pass-through mode**. 
Enable **WIFIxpresso** to be able to send and receive commands to the console through therminal WiFly module **without** the LPC1115 interfere.
In order to enable this mode follow the following steps:

1. Insert the jumper connector **J1**

2. connect the **level shifter** to **CN1**

::

 PIN1 = LPC_UART_RX
 PIN2 = LPC_UART_TX
 PIN3 = GND

3. open a terminal (hyper terminal or other) and use the free **Baud: 9600, 8bit, Flow: None, 1 stop bit**

4. start the demo

| At this point it is possible to **send commands** from the terminal and **receive response messages**. 
| For example, you can reset the module to factory defaults :ref:`factoryreset`.
| 
| For more information, refer to the document **WiFly User Manual** from the site by clicking http://www.microchip.com/wwwproducts/Devices.aspx?dDocName=en558369 under **Documentation & Software**.

