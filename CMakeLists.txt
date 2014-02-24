cmake_minimum_required(VERSION 2.8.3)
project(udpclient)

if(NOT CMAKE_CONFIGURATION_TYPES AND NOT CMAKE_BUILD_TYPE)
  set(CMAKE_BUILD_TYPE Release)
endif()

find_package(catkin REQUIRED COMPONENTS
roscpp)

find_package(Boost REQUIRED COMPONENTS system)
find_package(PkgConfig)


include_directories( ${Boost_INCLUDE_DIR} ${catkin_INCLUDE_DIRS})


link_directories(${catkin_LIBRARY_DIRS})

add_executable(udpclient 
  src/udpclient.cpp)

target_link_libraries(udpclient 
  ${catkin_LIBRARIES}
)




