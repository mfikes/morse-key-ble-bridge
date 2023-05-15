cmake_minimum_required(VERSION 3.13.1)

find_package(Zephyr REQUIRED HINTS $ENV{ZEPHYR_BASE})
project(brige)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

target_sources(app PRIVATE
    src/main.c
    )

set(extra_includes
            "src"
            )

target_include_directories(app PUBLIC ${extra_includes})
