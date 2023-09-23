# Set the minimum required CMake version
cmake_minimum_required(VERSION 3.0)

# Project name
project(Lua)

set(LUA_LIB_SRCS 
    "lapi.c"
    "lcode.c"
    "lctype.c"
    "ldebug.c"
    "ldo.c"
    "ldump.c"
    "lfunc.c"
    "lgc.c"
    "llex.c"
    "lmem.c"
    "lobject.c"
    "lopcodes.c"
    "lparser.c"
    "lstate.c"
    "lstring.c"
    "ltable.c"
    "ltm.c"
    "lundump.c"
    "lvm.c"
    "lzio.c"
    "lauxlib.c"
    "lbaselib.c"
    "lcorolib.c"
    "ldblib.c"
    "liolib.c"
    "lmathlib.c"
    "loadlib.c"
    "loslib.c"
    "lstrlib.c"
    "ltablib.c"
    "lutf8lib.c"
    "linit.c"
)

file(GLOB_RECURSE LUA_HEADERS "*.h")

# Create the static library
add_library(${PROJECT_NAME} STATIC ${LUA_LIB_SRCS})

# Install the static library
install(TARGETS ${PROJECT_NAME} ARCHIVE DESTINATION ${CMAKE_INSTALL_LIBDIR})

# Install headers
install(FILES ${LUA_HEADERS} DESTINATION "${CMAKE_INSTALL_INCLUDEDIR}/Lua")

