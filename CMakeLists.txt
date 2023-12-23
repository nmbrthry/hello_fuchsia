cmake_minimum_required(VERSION 3.10)
project(HelloWorld)
add_executable(HelloWorld hello.cc)

find_library(FDIO NAMES fdio REQUIRED PATHS /lib)
find_library(ZIRCON NAMES zircon REQUIRED PATHS /lib)
target_link_libraries(HelloWorld ${FDIO} ${ZIRCON})

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -fno-exceptions")
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -fno-rtti")
