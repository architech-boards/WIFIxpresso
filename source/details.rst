Firmware Details
================

.. index:: Webserver tips

This project is taken from `LPCOPEN v1.03 <http://www.lpcware.com/content/nxpfile/lpcopen-platform>`_. The starting demo project taken from lpcopen is *nxp_xpresso_11c24_periph_uart*. After which it was ported the project microchip '`RN171 and RN131 PICtail WebServer <http://www.microchip.com/stellent/idcplg?IdcService=SS_GET_PAGE&nodeId=1406&dDocName=en559511>`_'. From the design of microchips improvements have been made in the management of web server software, the main changes are in **sys_tasks.c**:

* The sending of the icon **favicon.ico**. Browsers require this icon automatically after loading an html page. Do not send it determines the possible malfunction of certain browser.

* The web server closes the connection after 0.5 seconds if the browser does not need any page. This system prevents that the browser manage in their own way the connection with the server.

**RN-131C** handles only one socket at a time, the web server can properly handle a socket at a time.

.. index:: Modify software

Modify Software
---------------

For customers who desire to connect the module to a cloud server of their own choosing, instead of of the default http://mtt.mchpcloud.com, the changes required to the demo http-client application are quite simple. Follow these steps to change the cloud server:

In the **LPCXpresso IDE**, locate the following lines of code in the **wifly_util.h** file:

::

 #define NAME_VALUE "mtt.mchpcloud.com" // DNS name of host

| Change the value of the **NAME_VALUE** macro to the new designated cloud server, and re-build the project.
| The module, after associating with an access point that is connected to the Internet will, open a socket connection with the new cloud server and begin to make data requests.
| For customers who desire to build a more customized web-server and http client application, are encouraged to carefully review the file **sys_task.c**, and specifically the | function **TCPTasks()**. The **TCPTasks()** function is essentially a state machine. It sequences the module through all its phases of operation, from initialization, configuration, association, connection to server to operation as a http client.
| The current implementation of the demo does not have a file system, so all the html web pages are **pre-loaded in to memory**, with the **sys_task.c** file.

.. index:: Debug options

Debug options
-------------

* In options.h there are 2 defines:

::

 #define PRINTF_ENABLED 0
 #define VERBOSE_DEBUG 0

| Use these only if you want debug the code. These enables the function **printf** and it is used to display messages on the debug console of the IDE.

.. warning:: Use **printf** carefully because disables all interrupts temporarily when executed. Also stops the microcontroller execution if you do not use debug.


