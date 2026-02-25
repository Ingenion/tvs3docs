Feature Set
===========
The following diagram shows an overview of the TVS 3.0 feature set. 

.. figure:: ../../images/feature_set/feature-set.png
  :align: center

Mainframe
---------
The TVS 3.0 mainframe provides the following features shown in the diagram above.
 * FPGA: Opal Kelly XEM8310-AU25P (AMD Artix UltraScale+ XCAU25P-2FFVB676E)
 * Modules: 5 module slots (four Type 1, one Type 2) for customizing IO and functionality
 * Touchscreen: 10.4" QLED Quantum Dot Display, Capacitive Touch, High Brightness, wide-screen 1600×720 resolution, stereo speakers
 * Processing and display driver: Raspberry Pi-5 module (4GB RAM, 64-bit quad-core ARM Cortex-A76 CPU, VideoCore VII GPU)
 * Connectivity

   - Raspberry Pi - Gigabit Ethernet, WiFi 6E, Bluetooth 5.0, USB 3.0

   - FPGA - SFP+ cage for multi-Gbps Ethernet or optical communication, USB-C for JTAG, USB-C for programming and communication

 * Power 

   - Single +12V DC input
   
   - +3.3V and +12V power to modules 
   
   - IO voltage to modules

 * Cooling: Active cooling with a high-quality fan and heatsink
 * FPGA I/O: 24 GPIO bidirection single-ended lines to each of 5 module slots, 8 full duplex GTX interfaces to slot 5 
 * RPi5 I/O: 2 unique GPIO lines to each slot, 2 shared GPIO lines to all slots 
 * 1 shared I2C bus between slots 1-3 and another shared I2C bus between slots 4 and 5

TVS FPGA (XEM8310-AU25P)
------------------------
The TVS 3.0 contains an Opal Kelly XEM8310-AU25P FPGA board which employs an AMD Artix UltraScale+
XCAU25P-2FFVB676E.  For details on the features of the Opal Kelly board, please refer to the Opal Kelly XEM8310-AU25_ User Manual.

.. _XEM8310-AU25: https://opalkelly.com/products/xem8310/

The XEM8310-AU25P board provides a USB-C interface for programming and communication with the FPGA using the Opal Kelly-provided API and USB driver.  

The XEM8310-AU25P board also provides a JTAG interface to the FPGA which is accessible via another USB-C connector.  The JTAG interface can also be used for programming the FPGA as well as for debugging purposes.  With the free Vivado toolset, the JTAG interface provides access to internal logic analyzers (ILA) and virtual input/output (VIO) cores that provide observability into the internal operation of the FPGA.  With the Vitis toolset, the JTAG interface can be used to develop and debug SoC applications inside the FPGA.

The TVS 3.0 provides an SFP+ cage for high-speed serial communication.  SPF+ modules can be plugged into the cage to provide multi-Gbps Ethernet communication to the FPGA.

.. _type1_io_details:

Modules
-----------
The TVS 3.0 mainframe accepts two types of modules.

**Type 1**

  Slots 1-4 provide the following interfaces on an edge connector.
   * 24 GPIO bidirection single-ended lines to the TVS FPGA
   * 1 shared I2C bus between slots 1-3 and another shared I2C bus between slots 4-5
   * 2 unique GPIO lines to the RPi5
   * 2 shared GPIO lines to the RPi5
   * IO voltage power
   * +3.3V power
   * +12V power

**Type 2**

  Slot 5 provides the same interfaces as Type 1 with the addition of the following.
   * 8 full duplex GTX interfaces to the TVS FPGA

Touchscreen
-----------
The TVS 3.0 sports a 10.4" QLED Quantum Dot Display, Capacitive Touch, High Brightness touchscreen with a resolution of 1600×720.  Internally, the touchscreen connects to the Raspberry Pi-5 module via HDMI (for video and audio) and USB (for touch input).  The touchscreen allows the RPi5 to be used as a standalone system without the need for an external monitor, keyboard, or mouse.  The touchscreen also provides stereo speakers for audio output.

Raspberry Pi-5
--------------
Combined with the touchscreen, the Rasberry Pi-5 module provides a familiar and flexible processing unit for the TVS 3.0.  Internally, the RPi5 module is connected to the TVS FPGA via standard SPI, UART, I2C, and 5 bidirectional IO lines.  It also connects to module slots 1-5 via 2 unique GPIO lines and 2 shared GPIO lines.

Externally, the RPi5 module also provides a Gigabit Ethernet port, WiFi 6E, Bluetooth 5.0, and USB 3.0 connectivity.

The RPi5 module runs a 64-bit operating system such as Raspberry Pi OS or Ubuntu.  It can be programmed in a variety of languages including Python, C/C++, and others.

The RPi5 module can be used to run high-level applications, provide network connectivity, and interface with the FPGA for control and data processing.
