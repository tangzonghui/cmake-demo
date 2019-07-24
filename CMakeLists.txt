# CMake 最低版本号要求
cmake_minimum_required (VERSION 2.8)
# 项目信息
project (Demo1)
set (Demo_VERSION_MAJOR 1)
set (Demo_VERSION_MINOR 0)
set(CMAKE_SYSTEM_PROCESSOR arm)

set(CMAKE_SYSTEM_NAME Linux)
set(CMAKE_SYSTEM_PROCESSOR arm)

set(CMAKE_SYSROOT /home/sw/tangzh/pie/android-ndk-r20/my-toolchain/sysroot)

set(tools /home/sw/tangzh/pie/android-ndk-r20/my-toolchain)
set(CMAKE_C_COMPILER ${tools}/bin/arm-linux-androideabi-gcc)
#set(CMAKE_CXX_COMPILER ${tools}/bin/arm-linux-androideabi-g++)

set(CMAKE_FIND_ROOT_PATH_MODE_PROGRAM BOTH)
set(CMAKE_FIND_ROOT_PATH_MODE_LIBRARY ONLY)
set(CMAKE_FIND_ROOT_PATH_MODE_INCLUDE ONLY)
set(CMAKE_FIND_ROOT_PATH_MODE_PACKAGE ONLY)

# 指定生成目标
configure_file (
      "${PROJECT_SOURCE_DIR}/config.h.in"
      "${PROJECT_BINARY_DIR}/config.h"
      )
option (USE_MYMATH
       "Use provided math implementation" ON)
add_executable(Demo main.cc)
