# SPDX-License-Identifier: Apache-2.0

cmake_minimum_required(VERSION 3.20.0)
find_package(Zephyr REQUIRED HINTS $ENV{ZEPHYR_BASE})
project(peripheral_esp)

FILE(GLOB app_sources src/*.c)
target_sources(app PRIVATE ${app_sources})

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

target_sources(app PRIVATE
  src/main.c
)

zephyr_library_include_directories(${ZEPHYR_BASE}/samples/bluetooth)

