# write by zhang ning 2018/3/19 16:05
cmake_minimum_required(VERSION 2.8)
 
project(disparity)

set( CMAKE_BUILD_TYPE "Debug" )

set( CMAKE_CXX_FLAGS "-std=c++11 -O3" ) 
set(CMAKE_MODULE_PATH /home/zn/opencv-3.1.0/release)

# 寻找OpenCV库
find_package( Opencv REQUIRED )
if(Opencv_FOUND)
    message(STATUS "The OpenCV lib is found!")
endif()

find_package( Pangolin REQUIRED)


include_directories( "/usr/include/eigen3" )
include_directories( ${Pangolin_INCLUDE_DIRS} )

add_executable(disparity disparity.cpp)
target_link_libraries(disparity ${OpenCV_LIBS} ${Pangolin_LIBRARIES})
