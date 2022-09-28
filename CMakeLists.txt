# CMakeLists.txt --- CMake project settings
#    ex) cmake -G "Visual Studio 9 2008" .
#    ex) cmake -DCMAKE_BUILD_TYPE=Release -G "MSYS Makefiles" .
##############################################################################

# CMake minimum version
cmake_minimum_required(VERSION 3.0)

# project name and languages
project(NoActivate CXX RC)

##############################################################################

# Microsoft Visual C++?
if(MSVC)
    add_definitions(-DMSVC)
endif()


# NoActivate.exe
add_executable(NoActivate WIN32 NoActivate.cpp NoActivate_res.rc)
target_compile_definitions(NoActivate PRIVATE UNICODE _UNICODE)
target_link_libraries(NoActivate comctl32)

##############################################################################
