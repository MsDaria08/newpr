cmake_minimum_required(VERSION 3.18)

set(CMAKE_CXX_STANDARD 14)

include("cmake/HunterGate.cmake")

HunterGate(
        URL "https://github.com/MsDaria08/hunter/archive/v1.1.tar.gz"
        SHA1 "b766fb97c2a919e67030580a39dede2a1f76c180"
)

project(newpr)
hunter_add_package(factorial)
find_package(factorial CONFIG REQUIRED)

add_executable(newpr main.cpp)

target_link_libraries(${PROJECT_NAME} factorial)

nstall(TARGETS ${PROJECT_NAME} RUNTIME DESTINATION bin)