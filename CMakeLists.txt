cmake_minimum_required(VERSION 3.13)

# Avoid warning about DOWNLOAD_EXTRACT_TIMESTAMP in CMake 3.24.
if (CMAKE_VERSION VERSION_GREATER_EQUAL "3.24.0")
        cmake_policy(SET CMP0135 NEW)
endif()

set(CMAKE_OSX_DEPLOYMENT_TARGET "11.0" CACHE STRING "Minimum OS X deployment version")

set(PROJECT_NAME freedv-integrations)
set(PROJECT_VERSION 2.4.1)
set(PROJECT_DESCRIPTION "Officially supported FreeDV radio integrations")
set(PROJECT_HOMEPAGE_URL "https://freedv.org")

if(APPLE)
    project(
        ${PROJECT_NAME}
        VERSION ${PROJECT_VERSION}
        DESCRIPTION ${PROJECT_DESCRIPTION}
        HOMEPAGE_URL ${PROJECT_HOMEPAGE_URL}
        LANGUAGES C CXX OBJCXX
    )
else()
    project(
        ${PROJECT_NAME}
        VERSION ${PROJECT_VERSION}
        DESCRIPTION ${PROJECT_DESCRIPTION}
        HOMEPAGE_URL ${PROJECT_HOMEPAGE_URL}
        LANGUAGES C CXX
    )
endif(APPLE)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

set(FreeDV_VERSION ${PROJECT_VERSION})
#set(FREEDV_VERSION_TAG "dev") # to indicate non-official release

#       
# Find the git hash if this is a working copy.
#       
include(cmake/CheckGit.cmake)
CheckGitSetup()

add_subdirectory(src)
