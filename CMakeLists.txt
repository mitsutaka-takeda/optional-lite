# Copyright 2016 by Martin Moene
#
# https://github.com/martinmoene/optional-lite
#
# This code is licensed under the MIT License (MIT).

cmake_minimum_required( VERSION 3.6 )

project( optional_lite )

option(OptionalLite_Tests "Enable testing for optional_lite" OFF)

add_library(OptionalLite INTERFACE)
add_library(OptionalLite::OptionalLite ALIAS OptionalLite)

target_include_directories(
  OptionalLite
  INTERFACE
  include/nonstd/
  )

if(OptionalLite_Tests)
  enable_testing()
  add_subdirectory( test )
endif()

#add_subdirectory( example )

# end of file
