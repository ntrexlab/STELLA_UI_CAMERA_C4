cmake_minimum_required(VERSION 2.8.3)
project(stella_ui_camera)

find_package(catkin REQUIRED COMPONENTS
        rospy std_msgs message_generation
        )

add_message_files(
  FILES
  Robot_status.msg
)

generate_messages(
  DEPENDENCIES
  std_msgs
  )

catkin_package(
        CATKIN_DEPENDS rospy std_msgs message_runtime
)

#catkin_install_python(PROGRAMS
#        scripts/rtmgr.pyc
#        scripts/stella_ui_dialog.pyc
#        DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION})

install(PROGRAMS
        DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}/scripts)

install(FILES
        scripts/map.yaml
        scripts/rtmgr_icon.xpm
        scripts/rtmgr.wxg
        DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION})

install(FILES
        scripts/images/autoware_logo_1.png
        scripts/images/autoware_logo_2_white.png
        DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}/images
        )

install(FILES
        DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}/launch_files
        )

install(DIRECTORY launch/
        DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}/launch
        PATTERN ".svn" EXCLUDE)

