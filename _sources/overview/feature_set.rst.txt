Feature Set
===========
The following diagram shows an overview of the TVS 3.0 feature set. 

.. figure:: ../../images/feature_set/feature-set.png
  :align: center

TVS FPGA (XEM8310-AU25P)
------------------------
The TVS 3.0 contains an Opal Kelly XEM8310-AU25P FPGA board which employs an AMD Artix UltraScale+
XCAU25P-2FFVB676E.  For details on the features of the Opal Kelly board, please refer to the Opal Kelly XEM8310-AU25_ User Manual.

.. _XEM8310-AU25: https://opalkelly.com/products/xem8310/

The XEM8310-AU25P board provides a USB-C interface for programming and communication with the FPGA using the Opal Kelly-provided API and USB driver.  

The XEM8310-AU25P board also provides a JTAG interface to the FPGA which is accessible via another USB-C connector.  The JTAG interface can also be used for programming the FPGA as well as for debugging purposes.  With the free Vivado toolset, the JTAG interface provides access to internal logic analyzers (ILA) and virtual input/output (VIO) cores that provide observability into the internal operation of the FPGA.  With the Vitis toolset, the JTAG interface can be used to develop and debug SoC applications inside the FPGA.

The TVS 3.0 provides an SFP+ cage for high-speed serial communication.  SPF+ modules can be plugged into the cage to provide multi-Gbps Ethernet communication to the FPGA.

Modules
-----------
The TVS 3.0 mainframe accepts two types of modules.

**Type 1**

  Slots 1-4 provide the following interfaces on an edge connector.
   * 24 GPIO bidirection single-ended lines to the TVS FPGA
   * 1 shared I2C bus between slots 1-3 and another shared I2C bus between slots 4-5
   * 2 unique GPIO lines to the Pi-5
   * 2 shared GPIO lines to the Pi-5
   * IO voltage power
   * +3.3V power
   * +12V power

**Type 2**

  Slot 5 provides the same interfaces as Type 1 with the addition of the following.
   * 8 full duplex GTX interfaces to the TVS FPGA

Touchscreen
-----------
The TVS 3.0 sports a 10.4" QLED Quantum Dot Display, Capacitive Touch, High Brightness touchscreen with a resolution of 1600×720.  Internally, touchscreen connects to the Raspberry Pi-5 module via HDMI (for video and audio) and USB (for touch input).  The touchscreen allows the Pi-5 to be used as a standalone system without the need for an external monitor, keyboard, or mouse. 

Raspberry Pi-5
--------------
Combined with the touchscreen, the Rasberry Pi-5 module provides a familiar and flexible processing unit for the TVS 3.0.  Internally, the Pi-5 module is connected to the TVS FPGA via standard SPI, UART, I2C, and 5 bidirectional IO lines.  It also connects to module slots 1-5 via 2 unique GPIO lines and 2 shared GPIO lines.

Externally, the Pi-5 module also provides a Gigabit Ethernet port, WiFi 6E, Bluetooth 5.0, and USB 3.0 connectivity.

The Pi-5 module can be used to run high-level applications, provide network connectivity, and interface with the FPGA for control and data processing.

