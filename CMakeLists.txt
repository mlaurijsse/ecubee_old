cmake_mimimum_required (VERSION 2.6)
project(ecubee)

set (ecubee_VERSION_MAJOR 0)
set (ecubee_VERSION_MINOR 1)

add_executable(ecubee main.cpp)

install(TARGETS ecubee DESTINATION bin)

# build a CPack driven installer package
include (InstallRequiredSystemLibraries)
set (CPACK_PACKAGE_VERSION_MAJOR "${ecubee_VERSION_MAJOR}")
set (CPACK_PACKAGE_VERSION_MINOR "${ecubee_VERSION_MINOR}")
include (CPack)
