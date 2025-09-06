cmake_minimum_required(VERSION 3.16)
project(algorithms-data-structures-1-4)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

set(CMAKE_AUTOMOC ON)

find_package(Qt6 COMPONENTS Widgets REQUIRED)

add_executable(algorithms-data-structures-1-4 "src/Main.cpp" "src/MainWindow.cpp"  "src/MainWindow.hpp")
target_link_libraries(algorithms-data-structures-1-4 Qt6::Widgets)

if (WIN32)
    set_property(TARGET algorithms-data-structures-1-4 PROPERTY WIN32_EXECUTABLE true)

    add_custom_command(
        TARGET algorithms-data-structures-1-4 POST_BUILD
        COMMAND ${Qt6_DIR}/../../../bin/windeployqt $<TARGET_FILE:algorithms-data-structures-1-4>
    )
endif (WIN32)
