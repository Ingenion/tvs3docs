Raspberry Pi-5
==============
The TVS 3.0 contains a `Raspberry Pi 5 <https://www.raspberrypi.com/products/raspberry-pi-5/>`_  (RPi5) as the main processing unit. The RPi5 is a powerful single-board computer that provides high performance and versatility for various applications. It features a quad-core ARM Cortex-A76 CPU, up to 8GB of RAM, making it suitable for demanding tasks and multimedia applications.

In the TVS, the RPi5 serves as the central hub for processing data, running software applications, and managing connectivity with other components. It is responsible for handling tasks such as data processing, user interaction, communication with peripherals, and running the operating system.

Connectivity
------------

**To the XEM Board**

Internally, the RPi5 is connected to the XEM board via GPIO, UART, and SPI interfaces which are natively supported by the RPi5.  These interfaces allow the RPi5/touchscreen pair to communicate with the XEM board for data exchange, control signals, and sensor interfacing.

Externally, the TVS 3.0 exposes the RPi5's USB ports, allowing users to connect the RPi5 to the XEM board over USB 3.0.  This allows RPi5 applications to load bit files into the XEM board and communicate with it.   

**To the Modules**

The RPi5 is connected to the various modules in the TVS 3.0 through a combination of GPIO, I2C, and SPI interfaces. These connections enable the RPi5 to control and communicate with the modules individually and as a group, allowing for data exchange, sensor readings, and control signals.

**External Interfaces**

The RPi5's connector side is exposed on the back of the TVS 3.0, allowing users to connect peripherals such as keyboards, mice, and external storage devices.  In addition, the RPi5's Gigabit Ethernet port is available for wired network connectivity, providing high-speed data transfer and reliable communication. 

The RPi5 also has built-in Wi-Fi 802.11ac and Bluetooth 5.0/BLE capabilities, enabling wireless connectivity for various applications.  These wireless features can be disabled with OS configuration for security purposes.

Software
--------
The RPi5 runs a Linux-based operating system, such as Raspberry Pi OS, which provides a user-friendly interface and access to a wide range of software applications. The RPi5 can be programmed using various programming languages, including Python, C++, and Java, allowing developers to create custom applications and scripts for the TVS.

For applications requiring automation, the RPi5 can run scripts and programs that interact with the XEM board and the connected modules, enabling automated tasks such as data acquisition, processing/analysis, pass/fail criteria evaluation, and control.  The RPi5's external interfaces allow for network data storage and logging, as well as remote access and control of the TVS.

A common application is to run a suite of automated tests on the TVS which have been developed in simulation with the DUT.  This scenario is described in the :ref:`tvs_concept` section and provides portability between the simulation environment and the lab test environment, a significant advantage for development and debugging.

In summary, the RPi5 can be used to run a wide range of applications, from quick and simple scripts to complex software solutions, making it a versatile component of the TVS 3.0.

The RPi5's Ethernet interface allows applications running on the TVS 3.0 to connect to a local network via sockets, enabling remote access, data transfer, and communication with other devices. This connectivity can be utilized for various purposes, such as remote monitoring and control, data logging, and accessing online resources.

The RPi5 can host an HTML server that serves a web-based user interface (UI) for the TVS 3.0. This UI can be accessed from any device on the same network, allowing users to interact with the TVS remotely through a web browser.  Such an application would allow the TVS to be the front-end server for hardware systems and subsystems connected to the TVS's modules.

Configuration
-------------
For security purposes, the RPi5's wireless interfaces (Wi-Fi and Bluetooth) can be disabled through the operating system's configuration settings. This can be done by modifying the appropriate configuration files or using command-line tools to disable the wireless interfaces. Disabling these interfaces can help prevent unauthorized access and enhance the security of the TVS 3.0 when it is deployed in environments where wireless connectivity is not required or desired.

Furthermore, it may be desired to disable the RPi5's Ethernet interface for security reasons.  This can also be accomplished through OS configuration, such as by disabling the network interface or configuring firewall rules to block network access.  Leaving only the USB interface enabled allows the RPi5 to communicate with the XEM board while preventing network access, which can be beneficial in certain secure environments.

The RPi5's EEPROM can be used to store configuration data for the TVS 3.0, such as module settings, network configurations, and user preferences. This allows the TVS to retain important information even when powered off, ensuring that it can quickly resume its previous state when powered back on. The EEPROM can be accessed and modified through software applications running on the RPi5, providing flexibility in managing the TVS's configuration.
