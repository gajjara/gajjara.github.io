## FIRST and Underwater Robotics: Final Year

<img src = "images/robotics_header.jpg?raw=true"/>

Caption: The underwater ROV designed.

**Context:**
In my final year of High School, I became the co-team lead of both my high school's FIRST Robotics Team (Team 97) and my high school's underwater robotics team.

For FIRST Robotics, I was not primarily involved in the design of the robot, my role was aimed toward managing the team as a whole and more administrative tasks.

For my underwater robotics team, I was primarily involved in the technical design of the robot, the project management, while not being primariluy involved in the managing of the team as a whole and the administrative tasks.

All credit goes to the 2018 FIRST Robotics Team 97 and the Cambridge Rindge and Latin School (CRLS) Underwater Robotics Team of 2018, and my advisors Conrad Hauck (for FIRST Team 97) and Paul McGuinness (for CRLS underwater robotics).

### FIRST Robotics
As stated above my role was primarily focusing on the team from a more administrative side. My role was:
- Occasionally managing the timeline of the development of the robot
- Developing safety protocols and practices
- Determining who can be on the drive team for the robot (i.e. the team that runs the robot)
- Obtaining funding for the team
- Managing travel to/from competitions
- Other smaller scale administrative tasks

The following images show an example of the work I did:

<img src = "images/robotics_first_ex_1.png?raw=true"/>

<img src = "images/robotics_first_ex_2.png?raw=true"/>

<img src = "images/robotics_first_ex_3.png?raw=true"/>

<img src = "images/robotics_first_ex_4.png?raw=true"/>

<img src = "images/robotics_first_ex_5.png?raw=true"/>

<img src = "images/robotics_first_ex_6.png?raw=true"/>

Caption: Examples of the work I did as the co-team lead.

For FIRST 2018, the competition was FIRST PowerUp, which involved tipping a scale or the switch in their favor to earn points, exchanging power cubes (milk crate sized cubes) into various ports, and climbing a scale tower. After weighing the scoring for tipping the scale/switch, exchanging power cubes, and climbing, we decided to design our robot for the exchanging of power cubes.

This involved two main mechanisms to be created: a shooting and gathering mechanism.

The following video shows our development throughout the FIRST 2018 season.

<video controls>
  <source src="/images/robotics_first_all.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

Caption: A video showing our development throughout the FIRST 2018 season.

With the design we all created, we won the Judges award for one of the New England FIRST 2018 competitons.

With the judges award being described as: 

"During the course of the competition, the judging panel encounters teams whose unique efforts, performance, or dynamics merit recognition yet do not fit into any of the existing award categories. Today, the judges have defined the following special award as The Shoot for the Moon Award for one such deserving team."

"The team's bold but calculated approach to their robot's origin was vindicated even when the STEAKS were high. Using a clever wheel intake mechanism to draw in and eject cubes from afar, the robot was the fasciniation of the field. Don't have a cow when we announce the recipient of this award. Congragulations: Team 97, Bionic Beef"

Again, all credit goes to the 2018 FIRST Team 97.

### Underwater Robotics
As mentioned above, my team-lead role for underwater robotics involved handling the technical design of our robot.

My underwater robotics team is involved in the Marine Advanced Technology Education Remotely Operated Vehicles New England Ranger Competition or MATE ROV NE Ranger Competition. The overall competition theme is to perform a wide variety of tasks in a specific environment. For the 2018 competition, the challenge was to locate the wreckage of an aircraft, identify the aircraft and retrieve its components, release and install scientific equipment to collect seismic data, locating the optimum region for tidal turbines, installing tidal turbines and related equipment, and monitoring and restoring marine habitats in the Pacific Northwest environment <a href="https://www.marinetech.org/files/marine/files/ROV%20Competition/2018%20competition/Missions/Updated%20manuals/2018%20RANGER%20Manual%20v9_6_3_14_2018_cover.pdf">(source)</a>. Note that since we were a high school this environment was simulated in a pool.

With these tasks, we decided to build an ROV with a single arm that can adaptively handle all the tasks above. 

This involved the following design elements:
- A lightweight frame to hold the motors, cameras, and the robotic arm
- A waterproof and reliable camera system
- A reliable propulsion system from motorized thrusters
- An arm with gribbing capabilities and wrist rotation
- A tether that allows ease of movement with the robot wihtout affecting buoyancy or 
- A simple buoyoancy system
- A reliable control system
- Effective yet simple safety features

**The Frame**

As commonly used for underwater ROV prototyping, a PVC frame is commonly used, as they are light, inexpensive, and malleable (to a certain extent). We built the frame in an octagan as this allows us to have several vertices to build off of, and is more hydrodynamic than other prism shapes. We placed 6 vertical pipes to connect the top and bottom frame to make the frame more robust, and allows us to attach our thrusters through contact points on the side of the robot. Overall, our frame sufficiently allowed the support of the thrusters, arm, and cameras.

<img src = "images/robotics_rov_frame.jpg?raw=true"/>

Caption: The ROV frame we designed.

**Cameras**

For the competition our team decided to utilize three cameras, using purchased cameras, we simply waterproofed them by encasing them in a PVC pipe and attaching marine grade silicone within the PVC pipe. These cameras output were directly fed into color LCD displays, and can be hooked up to a laptop to utilize digital measurement software.

<img src = "images/robotics_rov_camera.jpg?raw=true"/>

Caption: A waterproofed ROV camera.

**Propulsion**

We decided to propel our ROV with four Blue Robotics T100 thrusters. We decided to use these thrusters as these thrusters’ cores are sealed with marine-grade epoxy, and are tested up to 250V operation (way above our operating voltage of 12V). The thrusters also have a built-in cowling which prevents wires or other hazards being entangled in the blades. Thus the thruster is unlikely to fail during operation.

Two thrusters were mounted on the side columns of the ROV to control surge and yaw, while two thrusters were mounted on the top of the ROV to allow vertical movement. These thrusters provided five pounds of thrust, allowing relatively quick propulsion of the ROV under water.

<img src = "images/robotics_rov_thruster.png?raw=true"/>

Caption: A Blue Robotics T100 thruster.

**Robotic Arm**

Our arm was designed with two high torque motors in which one was for wrist rotation, and the other was for opening and closing the gripper. We decided to not implement any vertical rotation, as we could simply vertically rotate the bot using the thrusters we installed.

To open and close the gripper, we simply used a steel wire (to prevent snapping of the wire) attached on one end to a motor gear, while on the other end it was attached to the internal wire system of a trash gripper, while the wrist was rotated using a simple belt system.

Since we were utilizing DC motors, we simply decided to use a switch system for the control of the gripper arm and wrist rotation.

<img src = "images/robotics_rov_arm.png?raw=true"/>

Caption: The ROV arm.

**Tether**

We decided to build the tether with a wrap-around plastic sheathing, while adding foam woven in the plastic sheathing to allow the tether to have some positive buoyancy. This positive buoyancy does not obstruct the ROV's buoyancy (some effect on buoyancy, but this can be offset) or movement, since the tether floats above the neutrally buoyant ROV. Every electrical connection within the tether was covered with heat-shrink coated in epoxy in order to prevent any safety hazards or water damage.

<img src = "images/robotics_rov_tether.png?raw=true"/>

Caption: The ROV tether.

**Buoyancy**

Our buoyancy system was relatively simple, as we simply decided to use cutouts of diving board foam. We simply cut down the diving board foam until our ROV was neutrally buoyant in water.

We made sure to use a relatively large surface area of the diving board to ensure that any added loads that are attached to the ROV load does not significantly affect the buoyancy of the ROV.

This was also a simple low-cost solution for buoyancy on the ROV.

<img src = "images/robotics_rov_buy.png?raw=true"/>

Caption: The foam board attached to the ROV.

**Control System**

Our control system was a relatively simple system, in which we simply choose to use a Raspberry Pi running Python to read and process joystick inputs, an Arduino Uno utilizing Blue Robotics electronic speed controllers (ESCs) (for thruster control). 

We simply used the PyGame library to read inputs from a joystick that is connected via USB. We chose to the ESCs in order to allow for more precise control and simple control of the thrusters. 

This is the following flowchart for the control system:

<img src = "images/robotics_rov_flow.png?raw=true"/>

Caption: The flowchart for the control system.

**Other**

This is the following systems interconnection diagram for the overall system:

<img src = "images/robotics_rop_sid.png?raw=true"/>

Caption: The systems interconnection diagram.

**Safety**

For safety we decided to use the following safety procedures for the operation of the ROV:
- Ensure there are no sharp objects on or near the ROV
- Make sure that there are no conductible, semi-conductible objects or fluids in, on, or near the ROV
- Make sure all wires are properly secured, insulated, and waterproof
- Check that all motor connections, coverings, and mounts are properly secured
- Check the tether to ensure that there is not any missing insulation or waterproofing and that the tether is not knotted 
- Make sure the robotic arm is safely stowed either upwards or in front of the robot
- Ensure that all parts of the frame on the ROV are properly secure and will not disassemble from the ROV
- Be sure all personnel operating the ROV are wearing safety glasses
- Check the fuses to make sure they are not blown
- Be sure that all pressure vessels on the ROV are sealed
- Make sure all personnel and onlookers are clear from the area before operating the ROV
- Ensure that the electronics are on and running
- Check to make sure everyone is clear of the tether as the ROV is put in the water

**Competition**

In the competition we did not place as the top team (in the New England competition we had to place first to advance to the worldwide MATE competition), however the judges recognzied our team's communication and design when we were in the pool.

### Reflections
From both of my experiences on the teams I was able to obtain an extremely useful leadership experience from both an administrative and technical perspective. Thank you to all my teamates for their support and to my faculty advisors Conrad Huack and Paul McGuinness for mentoring me for 4 years on both robotics teams. 
