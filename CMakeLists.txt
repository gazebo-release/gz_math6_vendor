cmake_minimum_required(VERSION 3.10)
project(ignition_math6_vendor)

find_package(ament_cmake_core REQUIRED)
find_package(ament_cmake_vendor_package REQUIRED)


ament_vendor(ignition_math6_vendor
  VCS_URL https://github.com/ignitionrobotics/ign-math.git
  VCS_VERSION ignition-math6_6.9.2
  PATCHES patches
  CMAKE_ARGS
    -DBUILD_DOCS:BOOL=OFF
  GLOBAL_HOOK
)

find_package(ament_cmake_test REQUIRED)
if(BUILD_TESTING)
  find_package(ament_cmake_lint_cmake REQUIRED)
  find_package(ament_cmake_copyright REQUIRED)
  find_package(ament_cmake_xmllint REQUIRED)

  ament_lint_cmake()
  ament_copyright()
  ament_xmllint()
endif()

ament_package()
