cmake_minimum_required(VERSION 2.8 FATAL_ERROR)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

find_package(gazebo REQUIRED)
include_directories(${GAZEBO_INCLUDE_DIRS})
link_directories(${GAZEBO_LIBRARY_DIRS})
list(APPEND CMAKE_CXX_FLAGS "${GAZEBO_CXX_FLAGS}")

add_library(welcome SHARED script/welcome_message.cpp)
target_link_libraries(welcome ${GAZEBO_LIBRARIES})

add_library(model_push SHARED script/model_push.cpp)
target_link_libraries(model_push ${GAZEBO_LIBRARIES})
