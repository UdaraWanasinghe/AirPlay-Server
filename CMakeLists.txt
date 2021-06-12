cmake_minimum_required(VERSION 3.4.1)

project(airplay-server)

set (CMAKE_CXX_STANDARD 11)

add_subdirectory(lib/curve25519)
add_subdirectory(lib/ed25519)
add_subdirectory(lib/playfair)
add_subdirectory(lib/plist)
add_subdirectory(lib)
add_subdirectory(renderers)

add_executable( airplay-server airplay.cpp)
target_link_libraries ( airplay-server renderers airplay )

install(PROGRAMS airplay-server DESTINATION bin)

