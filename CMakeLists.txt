# Copyright (c) BBP/EPFL 2011-2015 Stefan.Eilemann@epfl.ch

# Never mind the [] sections. They are only here for doxygen.
# Remove them in your project.

# //! [Setup]
cmake_minimum_required(VERSION 3.1 FATAL_ERROR)
project(Hello VERSION 1.0.0)
set(Hello_VERSION_ABI 1)

list(APPEND CMAKE_MODULE_PATH ${PROJECT_SOURCE_DIR}/CMake
                              ${CMAKE_SOURCE_DIR}/CMake/common)
include(GitExternal)
# //! [Setup]

# //! [Scripts]
set(HELLO_DESCRIPTION "Example project for the Blue Brain Project")
set(HELLO_MAINTAINER "Blue Brain Project <bbp-open-source@googlegroups.com>")
set(HELLO_LICENSE LGPL BSD)

set(COMMON_PROJECT_DOMAIN ch.epfl.bluebrain)
include(Common)
common_find_package(Boost REQUIRED COMPONENTS unit_test_framework program_options)
common_find_package_post()
# //! [Scripts]

# //! [Targets]
add_subdirectory(hello)
add_subdirectory(apps)
add_subdirectory(tests)
# //! [Targets]

# //! [Footer]
include(CPackConfig)
include(DoxygenRule)
# //! [Footer]
