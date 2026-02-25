Interfaces
==========
This section provides an overview of the interfaces of the TVS mainframe and how they can be used in various scenarios.

Power
-----
The TVS is powered by a single external power supply, VDC_in.  Two connectors are provided for power delivery to the TVS mainframe.  

The first, J6, is a barrel jack connector that can be used with the standard AC-DC power supply that ships with the TVS mainframe.  Connector details are found `here <https://www.digikey.com/htmldatasheets/production/665130/0/0/1/pj-102ah.html?gclsrc=aw.ds&gad_source=1&gad_campaignid=120565755&gbraid=0AAAAADrbLlicA4SUiKmW5Obgdlr3wFmkb&gclid=EAIaIQobChMIiLKk9dXlkgMVrTbUAR3C_iSKEAAYASAAEgLRiPD_BwE>`_.

The second, J9, is a standard 9-pin D-sub male panel-mounted connector. The pinout is provided below.

.. list-table:: 
   :widths: 40 40
   :header-rows: 1

   * - **Net**
     - **Pins**
   * - *VDC_in*
     - *1, 2, 6, 7*
   * - *Ground*
     - *4, 5, 8, 9*

VDC_in has an opeating range of 8 to 14V.  The use of a regulated power supply is recommended with a voltage setting of 12.0V and a nominal current limit of TBD A.  VDC_in is used by the mainframe circuitry and routed to the modules, so the presence of any custom modules and how they use VDC_in should be taken into account when determining the power supply settings such as current limit, over-current protection, and slew rate.

**NOTE: Only one of the power connectors (J6 or J9) should be active as they are internally connected together.**

The front side of the TVS has a physical power switch that controls the power to the mainframe.  When the switch is in the "on" position, power is supplied to the mainframe and all components.  When the switch is in the "off" position, power is cut off to the mainframe and all components.  The power switch is a physical disconnect for safety purposes and should be used when connecting or disconnecting power to the TVS.  When a remotely controlled power supply is used to power the TVS, the power switch can be left in the "on" position and the remote power supply can be used to control the power to the TVS.


USB 3.0 to XEM8310
------------------
The back of the TVS 3.0 exposes a USB 3.0 Type-A connector that is connected to the XEM8310-AU25P FPGA board inside the mainframe.  This USB interface allows users to connect host computers to the TVS for programming and communication with the FPGA using the Opal Kelly-provided API and USB driver.  The USB 3.0 interface provides high-speed data transfer capabilities, enabling efficient programming and secure communication with the FPGA for various applications.

Note that the RPi5 can also perform the role of the host computer by connecting one of its USB ports to the XEM8310's USB port. 

USB 2.0/3.0 to RPi5
-------------------
The RPi5 provides two USB 3.0 Type-A ports and two USB 2.0 Type-A ports on the back of the TVS 3.0.  These ports can be used to connect peripherals such as keyboards, mice, and external storage devices to the RPi5.  In addition, one of these USB ports can be used to connect the RPi5 to the XEM8310's USB port, allowing the RPi5 to act as a host computer for programming and communication with the FPGA.

USB 3.0 to JTAG
---------------
For debugging XEM board FPGA designs, the TVS 3.0 provides a USB 3.0 Type-C connector that communicates with the JTAG interface of the XEM8310.  This allows users to use the JTAG interface for programming the FPGA as well as for debugging purposes.  With the free Vivado toolset, the JTAG interface provides access to internal logic analyzers (ILA) and virtual input/output (VIO) cores that provide observability into the internal operation of the FPGA.  With the Vitis toolset, the JTAG interface can be used to develop and debug SoC applications inside the FPGA.

Ethernet to RPi5
----------------
The RPi5 provides a Gigabit Ethernet RJ-45 port on the back of the TVS 3.0, allowing users to connect the RPi5 to a local network for remote access, data transfer, and communication with other devices.  This connectivity can be utilized for various purposes, such as remote monitoring and control, data logging, and accessing online resources.

SFP+ to XEM8310
---------------
The XEM8310-AU25P board provides support for an SFP+ cage for high-speed serial communication.  SPF+ modules can be plugged into the cage to provide multi-Gbps Ethernet communication to the FPGA.  This interface is ideal for applications requiring high-bandwidth and low-latency communication, such as network testing, data acquisition, and high-speed data transfer.  Additionally, the FPGA can implement other high-speed serial protocols over the SFP+ interface, such as PCIe, SpaceFibre, SRIO, and others, making it a versatile interface for various applications.
