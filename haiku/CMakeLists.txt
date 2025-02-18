cmake_minimum_required(VERSION 3.10)
project(haiku)

# Add executables
add_executable(haiku_server server.c)
add_executable(haiku_client client.c)

# Add socket library for Windows if needed
if(WIN32)
    target_link_libraries(haiku_server wsock32 ws2_32)
    target_link_libraries(haiku_client wsock32 ws2_32)
endif()
