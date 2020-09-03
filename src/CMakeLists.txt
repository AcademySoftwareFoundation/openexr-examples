# SPDX-License-Identifier: BSD-3-Clause
# Copyright Contributors to the OpenEXR Project.

cmake_minimum_required(VERSION 3.10)

project(openexr-examples)

find_package (OpenEXR)

add_executable(openexr-examples
  main.cpp
  drawImage.cpp
  generalInterfaceExamples.cpp
  generalInterfaceTiledExamples.cpp
  lowLevelIoExamples.cpp
  previewImageExamples.cpp
  rgbaInterfaceExamples.cpp
  rgbaInterfaceTiledExamples.cpp
)

target_link_libraries(openexr-examples OpenEXR::IlmImf)

if(WIN32 AND (BUILD_SHARED_LIBS OR OPENEXR_BUILD_BOTH_STATIC_SHARED))
  target_compile_definitions(IlmImfExamples PRIVATE OPENEXR_DLL)
endif()
