cmake_minimum_required(VERSION 3.0.2)
project(rviz_meshfile_display)


## Find catkin macros and libraries
## if COMPONENTS list like find_package(catkin REQUIRED COMPONENTS xyz)
## is used, also find other catkin packages
find_package(catkin REQUIRED COMPONENTS
  roscpp
  tf2
  tf2_geometry_msgs
  visualization_msgs
  dynamic_reconfigure  
)

# __ProtectedRegion_begin__ requirements
# find_package (Eigen3 3.3 REQUIRED NO_MODULE)
# find_package (Boost COMPONENTS <list boost libraries here>)
# __ProtectedRegion_end__ requirements

#########################
## Dynamic Reconfigure ##
#########################

generate_dynamic_reconfigure_options(
  cfg/rviz_meshfile_display.cfg
)


###################################
## catkin specific configuration ##
###################################
## The catkin_package macro generates cmake config files for your package
## Declare things to be passed to dependent projects
## LIBRARIES: libraries you create in this project that dependent projects also need
## CATKIN_DEPENDS: catkin_packages dependent projects also need
## DEPENDS: system dependencies of this project that dependent projects also need
catkin_package(
  INCLUDE_DIRS
  CATKIN_DEPENDS
    roscpp
    tf2
    tf2_geometry_msgs
    visualization_msgs
    dynamic_reconfigure
)

###########
## Build ##
###########

## Specify additional locations of header files
## Your package locations should be listed before other locations
include_directories(include)
include_directories(${catkin_INCLUDE_DIRS})

# __ProtectedRegion_begin__ includeStatements
# include_directories(${Boost_INCLUDE_DIRS})
# __ProtectedRegion_end__ includeStatements

## Declare cpp executable

# Node: rviz_meshfile_display
add_executable( rviz_meshfile_display src/rviz_meshfile_display.cpp )

target_link_libraries( rviz_meshfile_display ${catkin_LIBRARIES} )

add_dependencies(rviz_meshfile_display ${PROJECT_NAME}_gencfg )
add_dependencies(rviz_meshfile_display ${${PROJECT_NAME}_EXPORTED_TARGETS} )

# __ProtectedRegion_begin__ rvizMeshfileDisplayBuildStatements
# target_link_libraries( rviz_meshfile_display Eigen3::Eigen )
# target_link_libraries( rviz_meshfile_display ${Boost_LIBRARIES} )
# __ProtectedRegion_end__ rvizMeshfileDisplayBuildStatements


#############
## Install ##
#############


install(TARGETS rviz_meshfile_display
  ARCHIVE DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION}
  LIBRARY DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION}
  RUNTIME DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)


# __ProtectedRegion_begin__ other

# __ProtectedRegion_end__ other