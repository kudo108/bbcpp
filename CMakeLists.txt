cmake_minimum_required(VERSION 3.0)

project(bbcpp)
set(CMAKE_CXX_STANDARD 14)
set(CMAKE_MACOSX_RPATH 1)

if (UNIX)
    if (APPLE)
         set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++14 -stdlib=libc++ -ffunction-sections -fdata-sections -ftemplate-depth-256 -Wno-inconsistent-missing-override")
         set(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} -stdlib=libc++ -Wl,-dead_strip")
    endif (APPLE)
endif (UNIX)

if (NOT LIB_INSTALL_DIR)
    set (LIB_INSTALL_DIR "${CMAKE_INSTALL_PREFIX}/lib")
endif (NOT LIB_INSTALL_DIR)

add_subdirectory(lib)
add_subdirectory(examples)
add_subdirectory(tests)
