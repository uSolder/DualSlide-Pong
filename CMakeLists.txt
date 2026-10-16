cmake_minimum_required(VERSION 3.25)

# The DualSlide repository, which holds the game SDK, sits beside this one.
set(DUALSLIDE_DIR "${CMAKE_CURRENT_LIST_DIR}/../DualSlide" CACHE PATH "DualSlide repository")

if(NOT CMAKE_TOOLCHAIN_FILE)
    set(CMAKE_TOOLCHAIN_FILE "${DUALSLIDE_DIR}/software/sdk/cmake/toolchain.cmake")
endif()

project(Pong LANGUAGES C)

include("${DUALSLIDE_DIR}/software/sdk/cmake/DualSlideGame.cmake")

file(GLOB GAME_SOURCES CONFIGURE_DEPENDS "${CMAKE_CURRENT_LIST_DIR}/src/*.c")

dualslide_add_game(pong
    APP         Pong_App
    ID          dualslide.pong
    NAME        "Pong"
    VERSION     1.0.0
    AUTHOR      "Jack Herron"
    DESCRIPTION "Calm, modern Pong for one or two players."
    SOURCES     ${GAME_SOURCES}
    INCLUDES    "${CMAKE_CURRENT_LIST_DIR}/inc"
)
