cmake_minimum_required(VERSION 3.14)
project(facedetection)

set(CMAKE_CXX_STANDARD 17)
find_package(OpenCV REQUIRED)
include_directories( ${OpenCV_INCLUDE_DIRS} )

add_executable(facedetection main.cpp)
target_link_libraries(facedetection ${OpenCV_LIBS} )

# Print some message showing some of them
message(STATUS "OpenCV library status:")
message(STATUS "    version: ${OpenCV_VERSION}")
message(STATUS "    libraries: ${OpenCV_LIBS}")
message(STATUS "    include path: ${OpenCV_INCLUDE_DIRS}")

file(COPY model DESTINATION ${CMAKE_BINARY_DIR})
