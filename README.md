# rmi-mpsoc-ros

* What is this project? This project holds the delivarables for the last classwork for the Robótica Móvel Inteligente course of 2018/2. 

* How does this project work? Read the report (the PDF inside the root of the repo).

* Installing

  * Please, read the report! It is not well written but is enough to explain what the project is about. You can also e-mail me as well (andersondomingues@acad.pucrs.br).

 * You must clone both repositories (included as submodules) from git and follow the steps below. URSA repo is the simulation engine and hellfireos is the kernel. The application is deployed to hellfireos repo as well. Clone both repositories where you must, then copy (or move) `hellfireos` folder `into ursa/software/hellfireos`, inside URSA's directory tree.

  * Obtain a toolchain for the RiscV 32I architecture. You can get these either from Kriti (by sourcing `riscv23-elf`) or executing the script inside the `tools` folder from the hellfireos repo.

  * To compile the application, navigate to `ursa/software/hellfireos/platform/noc_4x4/` and make from there. If the directory is missing, you did not copy the contents of hellfireos onto `ursa/software/hellfireos`, and should go back to the first step (and potentially read everything again). If the compilation goes ok, you will see several `*.bin` files into the directory (along some other stuff). Copy all these `*.bin` files to `ursa/platforms/sulphane-generatic/bin`. 
  
  * To make the platform, navigate to `ursa/platforms/sulphane-generatic/bin` and make from there. The simulation should start briefly. To preview the simulation, run `ursa/tools/multitail.sh` from the  `ursa/platforms/sulphane-generatic` folder. You must have multitail installed in your system. I suggest using Terminator or another tool to help you handle the many terminals you will need to have open.
  
  * To run the PC part of the application, go to `ursa/tools/ros-integration` and run `catkin_make` from there. Of course you must have ROS installed. I tested with both ROS Kinect (Ubuntu 14.04) and Melodic (Debian 9 and Ubuntu 16.0x).
  
  * Once you build the catkin environment succefully, start the robot environment by launching Gazebo using the provided launch file. To do so, run ` ursa/tools/ros_integration/src/diff_drive_gazebo/run_gazebo.sh`. I tested this script using Gazebo9 and Gazebo7.
  
  * The last step is to bring up the network-bridge by start its ROS node. Type `roslaunch mpsoc_node mpsoc_node` from the catkin environment (to which you should be already). As soon as the node start you should see data popping into the terminal number 5 (remember to use the multitail script to inspect the platform).
`
  
  
  
  
  
 
