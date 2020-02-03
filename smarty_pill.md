## Generate Product Development: Smarty Pill

<img src="images/smarty_pill_sample_design.png?raw=true"/>
Caption: An example final implementation of the automatic pill dispenser.


**Goal:** Develop a prototype of an automatic and adaptive pill dispensing mechanism.

**Back Story:**
Our client to Generate Product Development with the idea to design a prototype of an automated pill dispenser. Our client had previously developed versions of an automated pill dispensers, however he encountered challenges with not being able to dispense pills of various sizes and shapes. Our deliverables for this product was to develop a pill dispensing mechanism that can adapt to all shapes and sizes of pills, develop a front end that allows user and caretaker registration, develop a backend (that holds user and caretaker data), develop a communication protocol between the backend server and a user device, prototype the user interface (UI) on a user device, develop a comprehensive firmware system, and develop a PCB for power management. Due to these deliverables, we were split into two teams, a hardware and software team. The hardware team was tasked with developing the mechanism, firmware, and power management, while the software team was tasked with developing the front end and back end, and the communication protocol. My role on the project involved protytping the UI, developing the firmware, and creating the power management PCB.

Credit goes to the <a href="https://web.archive.org/web/20191130065915/https://web.northeastern.edu/generate/our-team/"> Fall 2019 Smarty Pill Team</a> of Generate Product Development.

### Power Management PCB

The automated pill dispenser we were prototyping included a Raspberry Pi (for systems control), with stackable motor hats (for motor control of servos and steppers on the system), a touchscreen display, an LED and speaker (for feedback), a sensor system (for sensing the dispensing of pills), and an ADC. Due to the presence of all these systems, it was necessary that we build a PCB for centralized power management and cable organization. 

<img src = "images/smarty_pill_block_diagram.png?raw=true"/>
Caption: Block diagram of the system.

Due to the prescense of all these systems we built a PCB with the following considerations: 
- Allow easy access to GPIO pins on the Raspberry Pi 
- 12V and 5V power rails
- Access to the above power rails
- Access to an on-chip ADC
- Decoupling
- Charging/switching circuitry for backup battery 

Note that we decided to buy external electronic equipment for converting AC voltage to DC voltages.

With these considerations we came up with the following circuit design: 

<img src = "images/smarty_pill_schematic.png?raw=true"/>
Caption: Schematic of the Power Management PCB we designed.

With this schematic we then generated the following routing for the PCB: 

<img src = "images/smarty_pill_pcb_routing.png?raw=true"/>
Caption: The routing of the power management PCB.

While we were able to design the PCB, due to time constraints with the PCB fabrication, we were not able to fully implement the PCB. However, we were able to protoboard the system. The following video shows the electrical systems functioning properly.

<video controls>
  <source src="images/smarty_pill_electrical_v.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>
Caption: A video showing the functionality of the power management design.

After the project came to an end, the PCBs were fabricated.

<img src = "images/smarty_pill_pcbs.JPG?raw=true"/>
Caption: The fabricated PCB.

Credit goes to the computer and electrical engineers on the Fall 2019 SmartyPill team.

### Firmware Library

As mentioned above, due to the prescsense of several systems, we wanted to centralize the control of these systems in a Raspberry Pi; thus reqcquring us developing a comprehensive firmware library that covered all of the system we developed and allowed firmware for other systems to be easily added to the firmware library. Part of the firmware involved the communicaton channel between this user device on the Raspberry Pi and the backend server. We took an object oriented approach in designing the firmware. 

Before writing any code we defined the following structure for the firmware:

<img src = "images/smarty_pill_firmware_structure.png?raw=true"/>
Caption: The initial firmware structure we defined for the firmware.

Due to the ease of use we decided to write the firmware in Python.
Thus the following structure we defined earlier ended up looking this in Python:

<img src = "images/smarty_pill_firmware_structure_code.png?raw=true"/>
Caption: The structure of the firmware in Python.

The following image shows an example of a class we implemented in Python:

<img src = "images/smarty_pill_firmware_code_sc.png?raw=true"/>
Caption: An example of a class we implemented.

Once we finalized the firmware library, documentation was of paramount importance, the following image shows the README file we defined for the firmware library.

<img src = "images/smarty_pill_firmware_readme.png?raw=true"/>
Caption: The README file we wrote for the firmware libary.

Credit goes to the computer and electrical engineers on the Fall 2019 SmartyPill team.

<div style="display:none;"> ### User Interface Prototype 

Note to self: decide to show later. <img src="images/dummy_thumbnail.jpg?raw=true"/> </div>

### Reflections

The SmartyPill project that we took on at Generate Product Development was an ambitious project.
We had to develop a detailed project completely from scratch, and we ended up running into time constraint issues as the project approached an end.
Nontheless, we were succesfully able to develop an adaptable pill dispensing system, frontend and backend components, a communication protocol between the backend and user device, prototype the user interface, develop a firmware system, and develop a power management PCB. Our main challenge was that we either not able to fully fabricate a component or integrate all the components together.

All in all, we were able to prototype each system individually.

Overall, my experience on the SmartyPill project further introduced me to what it is like to work on a large project that involves at least a couple teams. I was introduced to more industry-facing concepts of computer and electrical engineering. My work on the power management PCB and firmware system further introduced me to firmware and embedded system development and circuit and PCB design.

Again, all credit goes to the Fall 2019 SmartyPill Team.
