XEM8310-A25U
============
The TVS 3.0 contains an Opal Kelly XEM8310-AU25P FPGA board which employs an AMD Artix UltraScale+
XCAU25P-2FFVB676E.  In addition to support for the Opal Kelly FrontPanel SDK_ and SuperSpeed USB 3.0, the XEM8310-AU25P module includes 2 GiB DDR4, clock oscillators, and three mezzanine expansion connectors for access to fabric and transceiver I/O. For more details on the features of the Opal Kelly board, please refer to the Opal Kelly XEM8310-AU25_ User Manual.

.. _XEM8310-AU25: https://opalkelly.com/products/xem8310/
.. _SDK: https://www.opalkelly.com/products/frontpanel/

The XEM8310-AU25P board provides a USB-C interface for programming and communication with the FPGA using the Opal Kelly-provided API and USB driver.  

The XEM8310-AU25P board also provides a JTAG interface to the FPGA which is accessible via another USB-C connector.  The JTAG interface can also be used for programming the FPGA as well as for debugging purposes.  With the free Vivado toolset, the JTAG interface provides access to internal logic analyzers (ILA) and virtual input/output (VIO) cores that provide observability into the internal operation of the FPGA.  With the Vitis toolset, the JTAG interface can be used to develop and debug SoC applications inside the FPGA.

The TVS 3.0 provides an SFP+ cage for high-speed serial communication.  SPF+ modules can be plugged into the cage to provide multi-Gbps Ethernet communication to the FPGA.


FPGA
----
The XEM8310-A25U contains a generously sized AMD Artix UltraScale+ XCAU25P-2FFVB676E FPGA. This FPGA features:
  * 252K Logic Cells
  * 16.5 Mb of Block RAM
  * 840 DSP Slices
  * much more

The FPGA provides 149 I/O and 12 GTY transceiver lanes for high-count and high-bandwidth connectivity to the TVS modules and other peripherals via high-speed expansion connectors.

The bit file for the FPGA can be programmed using either the Opal Kelly FrontPanel SDK or Xilinx Vivado toolset.  The FPGA can be programmed via the USB-C programming port or the JTAG port.  Additionally, the FPGA can be configured to load a bit file from an onboard SPI flash memory upon power-up so that no interaction is needed to program the FPGA after power is applied.

I/O
---
The following spreadsheet provides the mapping of the FPGA I/O to the various connectors and peripherals in the TVS 3.0 mainframe.  Use this spreadsheet as a reference when designing your own FPGA configuration for the TVS 3.0.

Excel format: :download:`TVS 3.0 IO Planning Spreadsheet <../_static/tvs3_io_planning.xlsx>`.


