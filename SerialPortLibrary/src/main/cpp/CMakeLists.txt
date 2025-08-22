cmake_minimum_required(VERSION 3.4.1)

add_library(SerialPort SHARED
            SerialPort.c)

# 设置链接器参数，保证 ELF 段对齐到 16KB
set(CMAKE_SHARED_LINKER_FLAGS "${CMAKE_SHARED_LINKER_FLAGS} -Wl,-z,max-page-size=16384")

# Include libraries needed for libserial_port lib
target_link_libraries(SerialPort
                      android
                      log)