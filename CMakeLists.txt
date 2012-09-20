cmake_minimum_required(VERSION 2.8)
project(ecubee)

set (ecubee_VERSION_MAJOR 0)
set (ecubee_VERSION_MINOR 1)

#include_directories("/usr/include")

add_executable(ecubee main.cpp)

target_link_libraries(ecubee osg)
target_link_libraries(ecubee osgViewer)
target_link_libraries(ecubee osgSim)
target_link_libraries(ecubee osgUtil)

install(TARGETS ecubee DESTINATION bin)

# build a CPack driven installer package
include (InstallRequiredSystemLibraries)
set (CPACK_PACKAGE_VERSION_MAJOR "${ecubee_VERSION_MAJOR}")
set (CPACK_PACKAGE_VERSION_MINOR "${ecubee_VERSION_MINOR}")
include (CPack)
