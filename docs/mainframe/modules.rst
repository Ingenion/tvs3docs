Modules
=======
There are two types of modules supported by the mainframe system.  Each module type has its own mechanical and electrical interface to the mainframe. The two module types are described below along with connectivity to resources inside the mainframe.

The diagram below shows the location of the module slots in the mainframe enclosure.

.. figure:: ../../images/mainframe/mainframe_back.png
   :align: center

Both module types receive 12V, 3.3V, and VIO power from the mainframe along with ground connections.  A Type 1 module can be installed in either a Type 1 or Type 2 module slot.  A Type 2 module can only be installed in a Type 2 module slot.

The pinout for each module slot is provide in the spreadsheet linked below.  Each slot has its own sheet in the spreadsheet.  Designers can use this spreadsheet to plan out their IO usage when designing custom modules.

Excel format: :download:`TVS 3.0 IO Planning Spreadsheet <../_static/tvs3_io_planning.xlsx>`.

Slots 1-3 share an I2C bus for inter-module communication.  Slots 4 and 5 share a separate I2C bus.  These two buses can be connected together via jumpers inside the mainframe.  Each module slot also has two unique GPIO lines to the Raspberry Pi-5 module and two shared GPIO lines to the Raspberry Pi-5 module.

Type 1
------
There are four Type 1 module slots in the mainframe, occupying slots 1-4. Type 1 modules provide a single edge connector interface, J1, to the mainframe.  Type 1 modules can provide a variety of I/O types to the FPGA including single-ended and differential signaling standards.  See :ref:`type1_io_details` for more I/O details.

Type 2
------
There is one Type 2 module slot in the mainframe, occupying slot 5.  Type 2 modules provide more I/O connectivity to the FPGA by using two edge connectors to the mainframe, J1 and J2.  J1 is compatible with Type 1 cards.  J2 is composed of GTY-type transceiver lanes, allowing for implementation of high-speed SERDES interfaces. See :ref:`type1_io_details` for more I/O details.

Module Mechanical Dimensions
----------------------------
The mechanical dimensions for Type 1 and Type 2 modules is shown below.  J2 is only used for Type 2 modules and can be omitted for Type 1 modules.  The PCB thickness is recommended to be 1.62 mm (0.063") with a maximum thickness of 2.00 mm (0.079").


+-------------------------------------------------------------+------------------------------------------------------------+
| .. figure:: ../../images/mainframe/module_pcb_dims.png      | .. figure:: ../../images/mainframe/module_envelope.png     |
|    :width: 800px                                            |    :width: 225px                                           |
|                                                             |                                                            |
|    PCB Dimensions                                           |    Envelope                                                |
+-------------------------------------------------------------+------------------------------------------------------------+


Note that the drawing for the Samtec `MEC1-120-02-L-D-A <https://suddendocs.samtec.com/prints/mec1-1xx-xx-xx-d-xx-xx-footprint.pdf?_gl=1*1j7qooo*_gcl_au*MTA3MDE5NTk3NC4xNzY1Mzc1OTYw*_ga*MTczNTYwNDMyMC4xNzY1Mzc1OTYx*_ga_3KFNZC07WW*czE3NjUzNzU5NjAkbzEkZzEkdDE3NjUzNzYxMDQkajIxJGwwJGg0MTMxNTIxNzQ>`_ Edge Connector specifies the following:

#. Card thickness range from 1.42mm to 1.72mm
#. 45 degree chamfer on bottom corners of card
#. 30 degree bevel on bottem edges of card going into the connector

Module Altium Templates 
-----------------------
Ingenion freely provides Altium Designer templates for both Type 1 and Type 2 modules to facilitate custom module development.  These templates include the mechanical outlines, mounting holes, and edge connector footprints needed to design a custom module.  If you are interested in receiving a link to the module template, please contact Ingenion using the link below. 

.. * Electrical Template: :download:`Download <https://www.ingenion.com/wp-content/uploads/2024/06/TVS3_Module_Template_Electrical.zip>` - pending release
.. * Mechanical Template: :download:`Download <https://www.ingenion.com/wp-content/uploads/2024/06/TVS3_Module_Template_Mechanical.zip>` - pending release
.. * Example Module Design: :download:`Download <https://www.ingenion.com/wp-content/uploads/2024/06/TVS3_Module_Example_Design.zip>` - pending release

.. // TODO <insert hyperlink to Altium templates on Altium 365 or GitHub>


Also, customers can contact Ingenion for assistance in designing and fabricating custom modules tailored to their specific application requirements.  Ingenion also offers a module design service where customers can provide their specifications and Ingenion will handle the design and fabrication of the custom module.
  * Contact: https://www.ingenion.com/contact/
  