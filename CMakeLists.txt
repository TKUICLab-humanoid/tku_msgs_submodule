cmake_minimum_required(VERSION 2.8.3)
project(tku_msgs)

## Compile as C++11, supported in ROS Kinetic and newer
# add_compile_options(-std=c++11)

## Find catkin macros and libraries
## if COMPONENTS list like find_package(catkin REQUIRED COMPONENTS xyz)
## is used, also find other catkin packages
find_package(catkin REQUIRED COMPONENTS
  message_generation
  sensor_msgs
)
##for kidsizebase send to strategy##
##imageprocess/vision##
add_message_files(DIRECTORY msg/vision
   	FILES 

	ButtonColorForm.msg
	CameraId.msg
	ColorData.msg
	ColorArray.msg
 	ObjectList.msg  
	DrawImage.msg
	HSVValue.msg
	LabelModelObjectList.msg 
	Distance.msg
	ImageLengthData.msg
	SoccerData.msg
	ImageProcess.msg
	ObservationData.msg
	Distance.msg
	LineData.msg
	FeaturePoint.msg
	Cooridinate.msg
	SoccerDataList.msg
	YoloData.msg
) 
##motionpackage##
add_message_files(DIRECTORY msg/motionpackage
   	FILES 

	callback.msg
	HeadPackage.msg
	PIDpackage.msg
	Parameter_message.msg
	Walking_message.msg
	InterfaceSend2Sector.msg
	SaveMotion.msg
	SaveMotionVector.msg
	SingleMotorData.msg
	SandHandSpeed.msg
	SensorPackage.msg
	SensorSet.msg
	Motor_Feedback.msg
) 
##usb_cam##
add_message_files(DIRECTORY msg/usb_cam
   	FILES 

	camera.msg
) 
##walkinggait##
add_message_files(DIRECTORY msg/walkinggait
   	FILES 

	Interface.msg
	parameter.msg
	wave.msg
	wavelist.msg
	B_SplineParam.msg
)
##Localization##
add_message_files(DIRECTORY msg/Localization
   	FILES 

	RobotPos.msg
	SetGoalPoint.msg
	SetRobotPos.msg
) 
##Ros2MultiCommunication##
add_message_files(DIRECTORY msg/Ros2MultiCommunication
   	FILES 

	WitchData.msg
	ObjectInfo.msg
	CharacterInfo.msg
	Ros2MultiCommunication.msg
)
##simmotionpackage##
add_message_files(DIRECTORY msg/simmotionpackage
   	FILES 

	IKinfo_message.msg
)
##imageprocess/vision##
add_service_files(DIRECTORY srv/vision 
	FILES 

	BuildModel.srv
	HSVInfo.srv
	SaveHSV.srv
)
##motionpackage##
add_service_files(DIRECTORY srv/motionpackage 
	FILES 

	CheckSector.srv
	ReadMotion.srv
	SendHandSpeed.srv
)
##usb_cam##
add_service_files(DIRECTORY srv/usb_cam 
	FILES 

	CameraInfo.srv
)
##walkinggait##
add_service_files(DIRECTORY srv/walkinggait 
	FILES 

	IKinfo.srv
	WalkingGaitParameter.srv
)

generate_messages(DEPENDENCIES std_msgs)

###################################
## catkin specific configuration ##
###################################
## The catkin_package macro generates cmake config files for your package
## Declare things to be passed to dependent projects
## INCLUDE_DIRS: uncomment this if your package contains header files
## LIBRARIES: libraries you create in this project that dependent projects also need
## CATKIN_DEPENDS: catkin_packages dependent projects also need
## DEPENDS: system dependencies of this project that dependent projects also need
catkin_package(
#  INCLUDE_DIRS include
#  LIBRARIES strategy
#  CATKIN_DEPENDS message_generation pluginlib roscpp std_msgs
#  DEPENDS system_lib
)

###########
## Build ##
###########

## Specify additional locations of header files
## Your package locations should be listed before other locations
include_directories(
  #include
  ${catkin_INCLUDE_DIRS}
)

## Declare a C++ library
#add_library(strategy_plugins src/strategy_plugins.cpp)

## Add cmake target dependencies of the library
## as an example, code may need to be generated before libraries
## either from message generation or dynamic reconfigure
# add_dependencies(${PROJECT_NAME} ${${PROJECT_NAME}_EXPORTED_TARGETS} ${catkin_EXPORTED_TARGETS})

## Declare a C++ executable
## With catkin_make all packages are built within a single CMake context
## The recommended prefix ensures that target name                                   s across packages don't collide
# add_executable(${PROJECT_NAME}_node src/strategy_node.cpp)

## Rename C++ executable without prefix
## The above recommended prefix causes long target names, the following renames the
## target back to the shorter version for ease of user use
## e.g. "rosrun someones_pkg node" instead of "rosrun someones_pkg someones_pkg_node"
# set_target_properties(${PROJECT_NAME}_node PROPERTIES OUTPUT_NAME node PREFIX "")

## Add cmake target dependencies of the executable
## same as for the library above
# add_dependencies(${PROJECT_NAME}_node ${${PROJECT_NAME}_EXPORTED_TARGETS} ${catkin_EXPORTED_TARGETS})

## Specify libraries to link a library or executable target against
# target_link_libraries(${PROJECT_NAME}_node
#   ${catkin_LIBRARIES}
# )

#############
## Install ##
#############

# all install targets should use catkin DESTINATION variables
# See http://ros.org/doc/api/catkin/html/adv_user_guide/variables.html

## Mark executable scripts (Python etc.) for installation
## in contrast to setup.py, you can choose the destination
# install(PROGRAMS
#   scripts/my_python_script
#   DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
# )

## Mark executables and/or libraries for installation
# install(TARGETS ${PROJECT_NAME} ${PROJECT_NAME}_node
#   ARCHIVE DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION}
#   LIBRARY DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION}
#   RUNTIME DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
# )

## Mark cpp header files for installation
# install(DIRECTORY include/${PROJECT_NAME}/
#   DESTINATION ${CATKIN_PACKAGE_INCLUDE_DESTINATION}
#   FILES_MATCHING PATTERN "*.h"
#   PATTERN ".svn" EXCLUDE
# )

## Mark other files for installation (e.g. launch and bag files, etc.)
# install(FILES
#   # myfile1
#   # myfile2
#   DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
# )

#############
## Testing ##
#############

## Add gtest based cpp test target and link libraries
# catkin_add_gtest(${PROJECT_NAME}-test test/test_strategy.cpp)
# if(TARGET ${PROJECT_NAME}-test)
#   target_link_libraries(${PROJECT_NAME}-test ${PROJECT_NAME})
# endif()

## Add folders to be run by python nosetests
# catkin_add_nosetests(test)
