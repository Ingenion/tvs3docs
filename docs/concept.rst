.. _tvs_concept:

Concept
=======

What is a *Total Verification System*?

When testing an electronics design's functionality, the interfaces of the design are the points where the test bench communicates with the :abbr:`DUT (Device Under Test)`.

.. list-table::
   :widths: 200 200

   * - .. image:: ../images/concept/basic-tb.png
     - As shown in this simplified diagram, the test bench stimulates the DUT's input interfaces and monitors the DUT's output interfaces.  The functionality implemented by the DUT is reflected in the DUT's output interfaces.

The TVS provides a programmable platform where the low-level interfaces (:abbr:`I/O (Input/Output)` components, protocol logic, buffers) are implemented in hardware, but the high-level tests, sequences, and :abbr:`API (Application Programming Interface)` /Drivers are implemented in software.  This approach allows the low-level interfaces to remain simple, powerful, and performant whereas the high-level test sequences are flexible, intelligent, and application-specific.  The diagram below illustrates this layered test bench approach with a loose mapping to the familiar :abbr:`OSI (Open Systems Interconnection)` model.

.. image:: ../images/concept/layered-tb.png
  :align: center

What makes the TVS different from other equipment is that test bench development starts in the world of simulation. The low-level interface blocks are implemented in programmable logic which becomes part of the simulation.  The high-level test bench is a combination of pre-existing software libraries and user-developed software that is customized for the design's requirements.

Everything developed in the simulation environment can be reused during card-level testing.  This portability between simulation and lab testing accelerates development and reduces cost.  Issues found in the lab can be easily recreated in simulation where observability is much greater, allowing issues to be addressed more efficiently.

Its programmability makes it well suited for use in simulation, card testing, box testing, and prototyping/emulation. 

Simulation
----------
Verifying designs with the TVS begins with simulation.  As shown below, the high-level tests communicate with your simulator tool using an abstraction layer provided by Ingenion that connects them to the low-level simulation models of the TVS hardware.

.. image:: ../images/concept/simulation-tb.png
  :align: center

Digital simulation tools (eg, QuestaSim, Riviera Pro) are used to simulate the DUT's :abbr:`RTL (Register Transfer Level)` along with Ingenion-provided simulation models of the lower-level TVS hardware.  The test harness which connects the TVS to the DUT is also part of the simulation.  Along with the DUT's HDL, the user is encouraged to generate and use simulation models of other components in their DUT (eg, :abbr:`SRAM (Static Random Access Memory)` devices, I/O devices, :abbr:`ADC (Analog to Digital Conversion)`/:abbr:`DAC (Digital to Analog Conversion)` devices, etc).  Increasing the fidelity of the simulation increases the potential to find bugs earlier in the design flow.

PyUVM
----------

Card Testing
------------

Box Testing 
-----------

Prototyping and Emulation
-------------------------

.. list-table:: 
   :widths: 20 200
   :header-rows: 0

   * - **Total**
     - *test bench development and use is involved from simulation, to card-testing, to system/sub-system testing*
   * - **Verification**
     - *focused on design testing*
   * - **System**
     - *hardware interfaces, user-programmable FPGA, libraries of software*
