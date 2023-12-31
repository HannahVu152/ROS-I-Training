Initialization and Global Variables
===================================

  In this exercise, we will take a first look at the main application
  :file:`pick_and_place_node.cpp`, its public variables, and how to properly
  initialize it as a ROS node.


Application Variables
---------------------

Open the file :file:`pick_and_place_utilities.h` in the following directory:

.. code-block:: cpp

  [workspace source directory]/pick_and_place_application/include/pick_and_place_application/

The C++ class ``PickAndPlaceConfig`` defines public global variables used
in various parts of the program. These variables are listed below:

.. literalinclude:: /../exercises/Perception-Driven_Manipulation/ros2/template_ws/src/pick_and_place_application/include/pick_and_place_application/pick_and_place_utilities.h 
  :start-after: PickAndPlaceConfig()
  :lines: 2-
  :dedent: 4
  :end-before: }
  :language: cpp

In the main program :file:`pick_and_place_node.cpp`, the global ``application``
object provides access to the program variables through its ``cfg`` member.

For instance, in order to use the ``WORLD_FRAME_ID`` global variable we would
do the following:

.. code-block:: cpp

  ROS_INFO_STREAM("world frame: " << application.cfg.WORLD_FRAME_ID)


Node Initialization
-------------------

In the :file:`pick_and_place_node.cpp` file, the following block of code in
the ``main`` function initializes the ``PickAndPlace`` application class and
its main ROS components.

.. literalinclude:: /../exercises/Perception-Driven_Manipulation/ros2/template_ws/src/pick_and_place_application/src/nodes/pick_and_place_node.cpp
  :start-at: int main(int argc, char** argv)
  :end-before: /* ========================================*/
  :language: cpp
