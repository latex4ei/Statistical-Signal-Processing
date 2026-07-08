cmake_minimum_required(VERSION 3.12)

project(Statistical-Signal-Processing NONE)
include(UseLATEX)

add_custom_target(
    writegitid ALL
    COMMAND ${CMAKE_CURRENT_SOURCE_DIR}/write-gitid.sh
    WORKING_DIRECTORY ${CMAKE_CURRENT_BINARY_DIR}
)

set(IMAGE_DIRS
    img
    # Add subdirectories here
    # img/logic
    # img/rca
)

add_latex_document(
    Statistical-Signal-Processing.tex
    FORCE_PDF
    IMAGE_DIRS ${IMAGE_DIRS}
    DEPENDS writegitid
)
