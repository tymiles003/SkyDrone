cmake_minimum_required(VERSION 3.7)
project(untitled)

set(CMAKE_CXX_STANDARD 11)

# Set up PCL Libraries
find_package(PCL 1.3 REQUIRED)
include_directories(${PCL_INCLUDE_DIRS})
link_directories(${PCL_LIBRARY_DIRS})
add_definitions(${PCL_DEFINITIONS})

# Set up OpenCV Libraries
find_package(OpenCV HINTS /usr/local/opt/opencv3 /usr/local/Cellar/opencv3 REQUIRED)


#include_directories("/usr/local/Cellar/opencv3/3.2.0/include/")

set(SOURCE_FILES main.cpp)
add_executable(untitled ${SOURCE_FILES})
include_directories(${OpenCV_INCLUDE_DIRS})
target_link_libraries(untitled ${PCL_COMMON_LIBRARIES} ${PCL_IO_LIBRARIES} ${OpenCV_LIBS})