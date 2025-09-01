cmake_minimum_required(VERSION 3.5)
project(nav2_msgs)

find_package(ament_cmake REQUIRED)
find_package(nav2_common REQUIRED)
find_package(builtin_interfaces REQUIRED)
find_package(nav_msgs REQUIRED)
find_package(geometry_msgs REQUIRED)
find_package(rosidl_default_generators REQUIRED)
find_package(std_msgs REQUIRED)
find_package(action_msgs REQUIRED)

nav2_package()

rosidl_generate_interfaces(${PROJECT_NAME}
  "msg/CollisionMonitorState.msg"
  "msg/Costmap.msg"
  "msg/CostmapMetaData.msg"
  "msg/CostmapFilterInfo.msg"
  "msg/SpeedLimit.msg"
  "msg/VoxelGrid.msg"
  "msg/BehaviorTreeStatusChange.msg"
  "msg/BehaviorTreeLog.msg"
  "msg/Particle.msg"
  "msg/ParticleCloud.msg"
  "msg/Route.msg"
  "msg/RouteNode.msg"
  "msg/RouteEdge.msg"
  "msg/EdgeCost.msg"
  "srv/GetCostmap.srv"
  "srv/IsPathValid.srv"
  "srv/ClearCostmapExceptRegion.srv"
  "srv/ClearCostmapAroundRobot.srv"
  "srv/ClearEntireCostmap.srv"
  "srv/DynamicEdges.srv"
  "srv/ManageLifecycleNodes.srv"
  "srv/LoadMap.srv"
  "srv/SaveMap.srv"
  "srv/SetInitialPose.srv"
  "srv/SetRouteGraph.srv"
  "action/AssistedTeleop.action"
  "action/BackUp.action"
  "action/ComputePathToPose.action"
  "action/ComputePathThroughPoses.action"
  "action/ComputeRoute.action"
  "action/ComputeAndTrackRoute.action"
  "action/DriveOnHeading.action"
  "action/SmoothPath.action"
  "action/FollowPath.action"
  "action/NavigateToPose.action"
  "action/NavigateThroughPoses.action"
  "action/Wait.action"
  "action/Spin.action"
  "action/DummyBehavior.action"
  "action/FollowWaypoints.action"
  DEPENDENCIES builtin_interfaces geometry_msgs std_msgs action_msgs nav_msgs
)

ament_export_dependencies(rosidl_default_runtime)

ament_package()


현재 나는 ROS2와 Nav2를 이용해서 모바일 로봇을 이용한 공기 청정 알고리즘을 구성하려고 한다.
여기서 나는 Agent.py 코드 밖에 수정하지 못하며, __init__에서 받는 인자를 변경할 수 없다.
이런 상황에서 nav2를 실행하여 a 포인트에서 b 포인트로 이동시키고 싶다. 
어떻게 해야하는가?