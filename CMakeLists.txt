cmake_minimum_required(VERSION 3.0)
project(classifier)

list(APPEND CMAKE_PREFIX_PATH "/path/to/libtorch")

find_package(OpenCV REQUIRED)
find_package(Torch REQUIRED)

include_directories( ${OpenCV_INCLUDE_DIRS} )
add_executable(classifier src/main.cpp)
target_link_libraries(classifier ${OpenCV_LIBS} ${TORCH_LIBRARIES})
# set C++14 to compile PyTorch
set_property(TARGET classifier PROPERTY CXX_STANDARD 14)
