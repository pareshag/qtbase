# Generated from hellovulkantexture.pro.

cmake_minimum_required(VERSION 3.14)
project(hellovulkantexture LANGUAGES CXX)

set(CMAKE_INCLUDE_CURRENT_DIR ON)

set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTORCC ON)
set(CMAKE_AUTOUIC ON)

set(INSTALL_EXAMPLEDIR "examples/vulkan/hellovulkantexture")

find_package(Qt6 COMPONENTS Core)
find_package(Qt6 COMPONENTS Gui)

add_qt_gui_executable(hellovulkantexture
    hellovulkantexture.cpp hellovulkantexture.h
    main.cpp
)
target_link_libraries(hellovulkantexture PUBLIC
    Qt::Core
    Qt::Gui
)


# Resources:
set(hellovulkantexture_resource_files
    "qt256.png"
    "texture_frag.spv"
    "texture_vert.spv"
)

qt6_add_resources(hellovulkantexture "hellovulkantexture"
    PREFIX
        "/"
    FILES
        ${hellovulkantexture_resource_files}
)

install(TARGETS hellovulkantexture
    RUNTIME DESTINATION "${INSTALL_EXAMPLEDIR}"
    BUNDLE DESTINATION "${INSTALL_EXAMPLEDIR}"
    LIBRARY DESTINATION "${INSTALL_EXAMPLEDIR}"
)
