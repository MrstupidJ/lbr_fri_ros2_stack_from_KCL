LBR Demos ROS 2 Control C++
===========================
Collection of basic usage examples for the ``lbr_hardware_interface`` through C++.

.. note::
    These examples can be run in simulation **and** on the real robot.

.. warning::
    Do always execute in simulation first, then in ``T1`` mode on the real robot.

Joint Trajectory Controller
---------------------------
Simulation
~~~~~~~~~~
#. Launch the ``LBRBringup``:

.. code-block:: bash

    ros2 launch lbr_bringup lbr_bringup.launch.py sim:=true model:=iiwa7 # [iiwa7, iiwa14, med7, med14]

#. Run the `lbr_joint_trajectory_executioner_node <https://github.com/lbr-stack/lbr_fri_ros2_stack/blob/foxy/lbr_demos/lbr_demos_ros2_control_cpp/src/lbr_joint_trajectory_executioner_node.cpp>`_:

.. code-block:: bash

    ros2 run lbr_demos_ros2_control_cpp lbr_joint_trajectory_executioner_node

The robot will twist, then move to the zero configuration.

Real Robot
~~~~~~~~~~
#. .. dropdown:: Launch the ``LBRServer`` application on the ``KUKA smartPAD``

    .. thumbnail:: ../../doc/img/applications_lbr_server.png

#. Select

    - ``FRI send period``: ``10 ms``
    - ``IP address``: ``your configuration``
    - ``FRI control mode``: ``POSITION_CONTROL`` or ``JOINT_IMPEDANCE_CONTROL``
    - ``FRI client command mode``: ``POSITION``
#. Proceed with steps 1 and 2 from `Simulation`_ but with ``sim:=false``.
