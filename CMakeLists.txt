#initialize project
cmake_minimum_required(VERSION 2.8)
project(ecubee)

set (ecubee_VERSION_MAJOR 0)
set (ecubee_VERSION_MINOR 1)

#include_directories("/usr/include")

add_executable(ecubee main.cpp)

# OSG libs
target_link_libraries(ecubee osg)
target_link_libraries(ecubee osgViewer)
target_link_libraries(ecubee osgSim)
target_link_libraries(ecubee osgUtil)

# Other libs
target_link_libraries(ecubee m)
target_link_libraries(ecubee dl)
target_link_libraries(ecubee GL)
target_link_libraries(ecubee GLU)
target_link_libraries(ecubee pthread)
target_link_libraries(ecubee Xext)
target_link_libraries(ecubee X11)

# Put Ecubee in bin dir
install(TARGETS ecubee DESTINATION bin)

# build a CPack driven installer package
include (InstallRequiredSystemLibraries)
set (CPACK_PACKAGE_VERSION_MAJOR "${ecubee_VERSION_MAJOR}")
set (CPACK_PACKAGE_VERSION_MINOR "${ecubee_VERSION_MINOR}")
include (CPack)
