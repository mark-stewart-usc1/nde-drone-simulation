One-time setup (already done — skip unless starting fresh)
px4_msgs and px4_ros_com cloned and built in ~/ws_ros2
VS Code Remote-SSH connected to VM
Every-time launch sequence

1. On Mac — start PX4 + Gazebo

cd ~/PX4-Autopilot
make px4_sitl gz_nde_drone

Wait for the pxh> prompt and the Gazebo window to appear.

If the Gazebo window doesn't show (says "gazebo already running"), clear stuck processes and relaunch:

pkill -9 -f "gz sim"; pkill -9 -f "gz-sim"; pkill -9 -f gzserver; pkill -9 -f ruby; pkill -9 -f px4
ps aux | grep -i gz     (confirm nothing but the grep line)
cd ~/PX4-Autopilot && make px4_sitl gz_nde_drone

(If it still won't show, gz sim -g in a second terminal, or reboot as last resort.)

2. On Mac — open QGroundControl
Open QGC, wait until it connects to the sim (shows the vehicle/telemetry).
Required — PX4 won't arm without a GCS connection.

3. In VM (terminal 1) — start the bridge

MicroXRCEAgent udp4 -p 8888

Leave it running. PX4's log should reconnect and re-create the /fmu topics.

4. In VM (terminal 2) — source and run the offboard node

cd ~/ws_ros2
source /opt/ros/humble/setup.bash
source ~/ws_ros2/install/setup.bash
ros2 run px4_ros_com offboard_control

5. Watch the Gazebo window — drone arms, ascends to ~5 m (16.5 ft), hovers.

To stop
Ctrl+C the offboard node (terminal 2)
To fully shut down cleanly: Ctrl+C the agent → shutdown in the pxh> prompt → close Gazebo
Verify clean: ps aux | grep -i gz (should be empty)
Key facts to remember
VM IP: 192.168.64.4 (can change on reboot — check UTM console if SSH fails)
SSH in: ssh mark_stewart@192.168.64.4
Setpoint line (in offboard_control.cpp): msg.position = {x, y, z} — NED frame, so negative z = up (−5.0 = 5 m up)
Rebuild after editing code: cd ~/ws_ros2 && colcon build && source install/setup.bash
If topics don't show: agent not running, or workspace not sourced, or IP changed
