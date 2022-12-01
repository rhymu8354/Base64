# CMakeLists.txt for Base64
#
# © 2018 by Richard Walters

cmake_minimum_required(VERSION 3.8)
set(This Base64)

set(Headers
    include/Base64/Base32.hpp
    include/Base64/Base64.hpp
)

set(Sources
    src/Base32.cpp
    src/Base64.cpp
)

option(${This}_BUILD_TESTING "Configure testing" ON)

add_library(${This} STATIC ${Sources} ${Headers})
set_target_properties(${This} PROPERTIES
    FOLDER Libraries
)

target_include_directories(${This} PUBLIC include)

if (${This}_BUILD_TESTING)
    add_subdirectory(test)
endif()
