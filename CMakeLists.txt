cmake_minimum_required(VERSION 3.16.3)

# ESP-IDF component wrapper for SdFat. Upstream ships only an Arduino
# library.properties, so the sources are registered here. `arduino` is
# required for SPI.h/Arduino.h, which SdFat's SPI driver depends on.

file(GLOB_RECURSE SDFAT_SRCS ${CMAKE_CURRENT_SOURCE_DIR}/src/*.cpp)

idf_component_register(SRCS ${SDFAT_SRCS}
                       INCLUDE_DIRS src
                       REQUIRES arduino libriccore)
