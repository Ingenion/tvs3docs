Product Sheet
=============

The Problem
-----------
Verification of digital designs can be a complicated, time-consuming, and expensive task.  As electronic devices get increasingly capable and designs become increasingly complicated, verifying proper functionality can be prohibitive to innovation and progress. Designs can easily demand a large amount of resources, long schedules, and deep pockets.  Furthermore, there is often inefficiency due to a replication of effort where it has suite is developed separately in both a simulation environment and the lab environment, sometimes by two separate teams.  Problems found in one environment are not easily re-created in the other environment.

The Solution
------------
The TVS 3.0 has been designed to take advantage of existing libraries, common interfaces, and standard protocols to make the process of design verification more efficient by leveraging reuse wherever possible.  This is accomplished by the availability of modules which support common industry standard I/O connected to a reprogrammable FPGA which is controlled by high-level software. All elements of the system are modeled in simulation where the DUT is developed. The system includes an abstraction layer which provides portability between the simulation and the lab environments allowing one test suite to be developed for both environments.

Feedback: Remove the word sequences.

.. figure:: ../../images/product_sheet/tvs-3.0-hi-level.png
  :align: center

The TVS 3.0 mainframe hosts up to 5 modules, each providing interfaces of a different I/O standard, allowing customers to mix-and-match modules to meet the I/O needs of their DUT.  See :ref:`module_set`.

Furthermore, the modular design of the TVS 3.0 allows customers to design their own modules to support user-specific I/O standards and contain custom electronics.  See :ref:`module_template`.

The Value
------------
When used early in design development, the TVS 3.0 has the potential to improve design reliability, and reduce schedule time and costs. It allows customers to quickly get started with writing high-level tests and sequences, leaving the lower layers to be provided by Ingenion.

In addition, the TVS also has the ability to prototype or emulate the DUT, allowing for the development of software or other systems which interface to the DUT.  See :ref:`emulation`.

Feedback:  Request email address for notifications.  Also, emphasize low risk and start simulation for free.
Action: Check with Opal Kelly about redistribution terms and conditions.
